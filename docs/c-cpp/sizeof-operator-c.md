# 操作员在 C 中的尺寸

> 原文:[https://www.geeksforgeeks.org/sizeof-operator-c/](https://www.geeksforgeeks.org/sizeof-operator-c/)

***Sizeof*** 是 [C 或 C++ ](https://www.geeksforgeeks.org/c-programming-language/) 中一个常用的运算符。这是一个编译时一元运算符，可用于计算其操作数的大小。sizeof 的结果是无符号整数类型，通常用 size_t 表示。sizeof 可以应用于任何数据类型，包括整型和浮点型等基元类型、指针类型或结构、联合等复合数据类型。
**用法**
*sizeof()* 运算符根据操作数类型使用方式不同。

**1。**当操作数是数据类型时。
当 *sizeof()* 用于 int、float、char 等数据类型时，它只返回分配给这些数据类型的内存量。
来看看例子:

## C

```cpp
#include <stdio.h>
int main()
{
    printf("%lu\n", sizeof(char));
    printf("%lu\n", sizeof(int));
    printf("%lu\n", sizeof(float));
    printf("%lu", sizeof(double));
    return 0;
}
```

## C++

```cpp
#include <iostream>
using namespace std;

int main()
{
    cout << sizeof(char)<<"\n";
    cout << sizeof(int)<<"\n";
    cout << sizeof(float)<<"\n";
    cout << sizeof(double)<<"\n";
    return 0;
}
```

**Output:** 

```cpp
1
4
4
8
```

**注意:** sizeof()可能会根据机器给出不同的输出，我们已经在 32 位 gcc 编译器上运行了我们的程序。

**2。**当操作数是表达式时。
当 *sizeof()* 与表达式一起使用时，它返回表达式的大小。让我们看看例子:

## C

```cpp
#include <stdio.h>
int main()
{
    int a = 0;
    double d = 10.21;
    printf("%lu", sizeof(a + d));
    return 0;
}
```

## C++

```cpp
#include <iostream>
using namespace std;
int main()
{
    int a = 0;
    double d = 10.21;
    cout << sizeof(a + d));
    return 0;
}
```

**Output:** 

```cpp
8
```

从第一种情况我们知道，int 和 double 的大小分别是 4 和 8，a 是 int 变量，而 d 是 double 变量。最终结果将是一个双字节，因此我们的程序输出是 8 字节。

**操作员类型**

sizeof()是编译时运算符。编译时间是指源代码转换为二进制代码的时间。它不执行()内部的代码。让我们看一个例子。

## C++

```cpp
#include <iostream>

using namespace std;
int main() {

 int y;

 int x = 11;

 y = sizeof(x++); //value of x doesn't change

 cout<<y<<" "<<x;// prints 4 11

}
```

如果我们试图增加 x 的值，它保持不变。这是因为，x 在括号内递增，sizeof()是编译时运算符。

**需要大小**T2**1。**找出数组中元素的个数。
Sizeof 可用于自动计算数组的元素个数。让我们看看例子:

## C

```cpp
#include <stdio.h>
int main()
{
    int arr[] = { 1, 2, 3, 4, 7, 98, 0, 12, 35, 99, 14 };
    printf("Number of elements:%lu ", sizeof(arr) / sizeof(arr[0]));
    return 0;
}
```

## C++

```cpp
#include <iostream>
using namespace std;

int main()
{
    int arr[] = { 1, 2, 3, 4, 7, 98,
    0, 12, 35, 99, 14 };
    cout << "Number of elements: "
    <<(sizeof(arr) / sizeof(arr[0]));
    return 0;
}
```

**Output:** 

```cpp
Number of elements: 11
```

**2。**到[动态分配一块内存](https://www.geeksforgeeks.org/dynamic-memory-allocation-in-c-using-malloc-calloc-free-and-realloc/)。
sizeof 广泛用于动态内存分配。例如，如果我们想要分配足以容纳 10 个整数的内存，而我们不知道特定机器中的 sizeof(int)。我们可以借助 sizeof 进行分配。

## C

```cpp
int* ptr = (int*)malloc(10 * sizeof(int));
```

**参考文献**
[【https://en.wikipedia.org/wiki/Sizeof】](https://en.wikipedia.org/wiki/Sizeof)
如有不正确的地方请写评论，或者想分享更多以上讨论话题的信息