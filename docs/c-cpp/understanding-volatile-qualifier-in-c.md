# 理解 C |集合 2 中的“volatile”限定词(示例)

> 原文:[https://www . geesforgeks . org/understand-volatile-qualifier-in-c/](https://www.geeksforgeeks.org/understanding-volatile-qualifier-in-c/)

volatile 关键字旨在防止编译器对对象应用任何可能以编译器无法确定的方式改变的优化。

在优化中省略了声明为 volatile 的对象，因为它们的值可以随时被当前代码范围之外的代码更改。系统总是从存储单元中读取易失性对象的当前值，而不是在请求时将其值保存在临时寄存器中，即使先前的指令向同一对象请求值也是如此。所以简单的问题是，变量的值如何以编译器无法预测的方式变化。考虑以下案例来回答这个问题。

*1)被作用域外的中断服务例程修改的全局变量:*例如，一个全局变量可以表示一个将被动态更新的数据端口(通常是指内存映射 IO 的全局指针)。代码读取数据端口必须声明为易失性，以便获取端口上可用的最新数据。如果没有将变量声明为 volatile，编译器将优化代码，只读取端口一次，并在临时寄存器中保持使用相同的值来加速程序(速度优化)。通常，当由于新数据的可用性而出现中断时，ISR 会更新这些数据端口

*2)多线程应用内的全局变量:*线程通信有多种方式，即消息传递、共享内存、邮箱等。全局变量是共享内存的弱形式。当两个线程通过全局变量共享信息时，它们需要用 volatile 限定。由于线程是异步运行的，任何由一个线程引起的全局变量的更新都应该由另一个消费线程重新获取。编译器可以读取全局变量，并将其放入当前线程上下文的临时变量中。为了消除编译器优化的影响，这些全局变量需要被限定为易变的

如果我们不使用 volatile 限定符，可能会出现以下问题
1)当优化打开时，代码可能无法按预期工作。
2)当启用和使用中断时，代码可能无法按预期工作。

让我们看一个例子来理解编译器如何解释 volatile 关键字。考虑下面的代码，我们正在使用指针改变 const 对象的值，我们正在编译没有优化选项的代码。因此编译器不会做任何优化，会改变常量对象的值。

## C

```cpp
/* Compile code without optimization option */
#include <stdio.h>
int main(void)
{
    const int local = 10;
    int *ptr = (int*) &local;

    printf("Initial value of local : %d \n", local);

    *ptr = 100;

    printf("Modified value of local: %d \n", local);

    return 0;
}
```

当我们使用 gcc 的“-save-temps”选项编译代码时，它会生成 3 个输出文件
1)预处理代码(具有。I)扩展)
2)汇编代码(具有。s 扩展)和
3)目标代码(具有。o 选项)。

我们在没有优化的情况下编译代码，这就是为什么汇编代码的大小会更大(下面用红色突出显示)。

**输出:**

```cpp
  [narendra@ubuntu]$ gcc volatile.c -o volatile –save-temps
  [narendra@ubuntu]$ ./volatile
  Initial value of local : 10
  Modified value of local: 100
  [narendra@ubuntu]$ ls -l volatile.s
  -rw-r–r– 1 narendra narendra 731 2016-11-19 16:19 volatile.s
  [narendra@ubuntu]$
```

让我们用优化选项(即-O 选项)编译相同的代码。在下面的代码中，“local”被声明为 const(并且是非易失性的)，GCC 编译器进行优化并忽略试图改变 const 对象值的指令。因此 const 对象的值保持不变。

## C

```cpp
/* Compile code with optimization option */
#include <stdio.h>

int main(void)
{
    const int local = 10;
    int *ptr = (int*) &local;

    printf("Initial value of local : %d \n", local);

    *ptr = 100;

    printf("Modified value of local: %d \n", local);

    return 0;
}
```

对于上面的代码，编译器会进行优化，这就是为什么汇编代码的大小会减少。

**输出:**

```cpp
  [narendra@ubuntu]$ gcc -O3 volatile.c -o volatile –save-temps
  [narendra@ubuntu]$ ./volatile
  Initial value of local : 10
  Modified value of local: 10
  [narendra@ubuntu]$ ls -l volatile.s
  -rw-r–r– 1 narendra narendra 626 2016-11-19 16:21 volatile.s
```

让我们将 const 对象声明为 volatile，并用优化选项编译代码。虽然我们用优化选项编译代码，const 对象的值会改变，因为变量被声明为 volatile，这意味着不做任何优化。

## C

```cpp
/* Compile code with optimization option */
#include <stdio.h>

int main(void)
{
    const volatile int local = 10;
    int *ptr = (int*) &local;

    printf("Initial value of local : %d \n", local);

    *ptr = 100;

    printf("Modified value of local: %d \n", local);

    return 0;
}
```

**输出:**

```cpp
  [narendra@ubuntu]$ gcc -O3 volatile.c -o volatile –save-temp
  [narendra@ubuntu]$ ./volatile
  Initial value of local : 10
  Modified value of local: 100
  [narendra@ubuntu]$ ls -l volatile.s
  -rw-r–r– 1 narendra narendra 711 2016-11-19 16:22 volatile.s
  [narendra@ubuntu]$
```

上面的例子可能不是一个好的实际例子，目的是解释编译器如何解释 volatile 关键字。举个实际的例子，想想手机上的触摸传感器。抽象触摸传感器的驱动程序将读取触摸的位置，并将其发送到更高级别的应用程序。驱动程序本身不应该修改(固定)读取位置，并确保每次读取触摸输入时都是新的(不稳定的)。这样的驾驶员必须以恒定的方式读取触摸传感器输入。

**注意:**以上代码是特定于编译器的，可能不适用于所有编译器。这些例子的目的是让读者理解这个概念。

**相关文章:**
[理解 C | Set 1 中的“volatile”限定词(简介)](https://www.geeksforgeeks.org/understanding-volatile-qualifier-c-set-1-introduction/)
有关 volatile 关键字的更多详细信息，请参考以下链接:
[Volatile:一个程序员最好的朋友](http://drdobbs.com/cpp/184403766)
[不要将 Volatile 用作同步原语](https://www.securecoding.cert.org/confluence/display/cplusplus/CON01-CPP.+Do+not+use+volatile+as+a+synchronization+primitive)
本文由“Narendra Kangralkar”编辑，GeeksforGeeks 团队审阅。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。