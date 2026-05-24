# C/c++ 中的协同词

> 原文:[https://www.geeksforgeeks.org/coroutines-in-c-cpp/](https://www.geeksforgeeks.org/coroutines-in-c-cpp/)

**什么是花冠？**
[Coroutines](https://www.geeksforgeeks.org/coroutine-in-python/) 是通用的控制结构，其中流程控制在两个不同的例程之间协作传递，而不返回。
如果你使用过 Python 或者 C#，你可能知道有一个关键字叫做 [yield](https://www.geeksforgeeks.org/use-yield-keyword-instead-return-keyword-python/) ，它允许在调用者和被调用的函数之间来回循环，直到调用者没有完成函数或者函数因为给定的一些逻辑而终止。
产量样本蟒 3 代码

## 计算机编程语言

```cpp
# A Python program to generate numbers in a
# range using yield

def rangeN(a, b):
    i = a
    while (i < b):
        yield i
        i += 1  # Next execution resumes
                # from this point   

for i in rangeN(1, 5):
        print(i)
```

输出:

```cpp
1
2
3
4
5 
```

这段代码演示了 yield 是如何工作的，并简要介绍了如何在调用方和被调用方之间更改控件。
**为什么需要花冠？**
要读取一个文件，并在读取到一些有意义的数据时对其进行解析，您可以在每行一步一步地读取，这很好。您也可以将整个内容加载到内存中，这对于大型文本情况是不推荐的，例如像微软 Word 这样的文本编辑器，或者在现代系统中只使用管道。
在《计算机编程的艺术》一书中，唐纳德·克努特提出了解决这类问题的方法。他的答案是完全抛弃堆栈概念。不要把一个过程看作是调用者，把另一个看作是被调用者，开始把他们看作是平等合作的。
所以我们现在可以试着看看如何在 C.
中达到同样的效果

```cpp
function read():
   /* reads the content in the desired number 
      of steps and returns back control to parser
      but saves its own state of function. */

function parse():
   a = read()
   while (a)
   {
       // do something
       a = read()
   }
```

实际上，这个结构看起来非常类似于 c 语言的调用者-被调用者结构。但是我们在这里要求的是读者必须记住它的状态。它必须记住上次工作时它在哪里，并且还应该是可重新设置的。
**如何在 C 语言中实现 Coroutines？**
面临的挑战是在 [C 语言中拥有协同程序，该语言本身是一种基于堆栈的语言](https://www.geeksforgeeks.org/memory-layout-of-c-program/)，即在 C 语言中对函数调用的每个响应中都有一个正在初始化的堆栈，该堆栈跟踪其所有变量和常数，当函数调用结束时，该堆栈就会被销毁。

## C

```cpp
int read(void)
{
    int i;
    for (i = 0; i < 10; i++)
        return i;   /* Well on the first run itself
                      the function will be destroyed */
}
```

我们需要做两件事:

1.  将控制恢复到最后状态
2.  通过调用保持数据

上述两个问题都应该通过使用静态变量来解决。但是如何记住状态并返回到与之前相同的执行状态，即返回或循环后的代码行。我们可以使用 GOTO 语句。一般不建议这样做。在这里，我们可以尝试一种叫做[达夫装置](https://www.geeksforgeeks.org/duffs-device-work/)的东西。
所以我们最后继续解决方案代码。

## C++

```cpp
// C++ program to demonstrate how coroutines
// can be implemented in C++.
#include <iostream>
using namespace std;

int range(int a, int b)
{
    static long long int i;
    static int state = 0;
    switch (state)
    {
    case 0: /* start of function */
        state = 1;
        for (i = a; i < b; i++)
        {
            return i;

        /* Returns control */
        case 1:; /* resume control straight
                    after the return */
        }
    }
    state = 0;
    return 0;
}

// Driver code
int main()
{
    int i; //For really large numbers

    for (; i=range(1, 5);)
        cout <<"control at main :"<< i << endl;

    return 0;
}

// This code is contributed by shivanisinghss2110
```

## C

```cpp
// C program to demonstrate how coroutines
// can be implemented in C.
#include<stdio.h>

int range(int a, int b)
{
    static long long int i;
    static int state = 0;
    switch (state)
    {
    case 0: /* start of function */
        state = 1;
        for (i = a; i < b; i++)
        {
            return i;

        /* Returns control */
        case 1:; /* resume control straight
                    after the return */
        }
    }
    state = 0;
    return 0;
}

// Driver code
int main()
{
    int i; //For really large numbers

    for (; i=range(1, 5);)
        printf("control at main :%d\n", i);

    return 0;
}
```

输出:

```cpp
control at range
control at main :1
control at range
control at main :2
control at range
control at main :3
control at range
control at main :4 
```

解决方案使用了我们对[达夫的设备](https://www.geeksforgeeks.org/duffs-device-work/)的理解，并让它玩。我们现在可以在 for 循环中有多个 return 语句，每次我们返回一个不同的执行状态，如果它被编程为这样做的话。此实现仅模仿 python 的[范围函数](https://www.geeksforgeeks.org/range-vs-xrange-python/)，该函数也基于 coroutine，因为它从 Python3 开始返回生成器对象。
**来源:**
[C 中的 Coroutines 西蒙·塔图姆](https://www.chiark.greenend.org.uk/~sgtatham/coroutines.html)
本文由**Rajat Kanti Bhattacharjee**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。