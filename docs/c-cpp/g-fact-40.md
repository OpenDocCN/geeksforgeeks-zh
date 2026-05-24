# c++ 中的预增量(或预减量)

> 原文:[https://www.geeksforgeeks.org/g-fact-40/](https://www.geeksforgeeks.org/g-fact-40/)

在 C++ 中，预增量(或预减量)可以作为 [l 值](https://www.geeksforgeeks.org/lvalue-and-rvalue-in-c-language/)，但后增量(或后减量)不能作为 l 值。

例如，以下程序打印 *a = 20* (++ a 用作 l 值)

```cpp
// CPP program to illustrate
// Pre-increment (or pre-decrement)
#include <cstdio>

int main()
{
    int a = 10;

    ++ a = 20; // works

    printf("a = %d", a);
    getchar();
    return 0;
}
```

```cpp
a = 20

```

上述程序运行正常，但以下程序编译失败，错误为*“赋值中的非左值”* (a++ 用作 l 值)

```cpp
// CPP program to illustrate
// Post-increment (or post-decrement)
#include <cstdio>

int main()
{
    int a = 10;
    a++ = 20; // error
    printf("a = %d", a);
    getchar();
    return 0;
}
```

```cpp
prog.cpp: In function 'int main()':
prog.cpp:6:5: error: lvalue required as left operand of assignment
 a++ = 20; // error 
     ^

```

**作为左值，++ a 和++ 有什么不同？**

这是因为`++ a`返回一个*左值*，它基本上是对我们可以进一步赋值的变量的引用——就像普通变量一样。它也可以分配给一个参考，如下所示:

```cpp
int &ref = ++ a; // valid
int &ref = a++ ; // invalid

```

然而，如果你回想一下`a++ `是如何工作的，它不会立即增加它所拥有的值。为简洁起见，您可以将其视为在下一条语句中递增。所以基本上发生的是`a++ `返回一个*值*，它基本上只是一个值，就像一个没有被存储的表达式的值一样。加工后可以想到`a++ = 20;`如下:

```cpp
int a = 10;

// On compilation, a++ is replaced by the value of a which is an rvalue:
10 = 20; // Invalid

// Value of a is incremented
a = a + 1;

```

这应该有助于理解为什么`a++ = 20;`不起作用。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。