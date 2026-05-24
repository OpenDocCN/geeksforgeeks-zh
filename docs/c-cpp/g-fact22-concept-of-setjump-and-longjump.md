# C

中的套跳和龙跳的概念

> 原文:[https://www . geeksforgeeks . org/g-fact 22-setjump-and-longump 的概念/](https://www.geeksforgeeks.org/g-fact22-concept-of-setjump-and-longjump/)

在 C 标准库中的头文件 [setjmp.h](https://en.wikipedia.org/wiki/Setjmp.h) 中定义了“Setjump”和“Longjump”。

*   **set jump (JMP _ bufbuf)** : use buf to remember the current position and return 0.
*   **Dragon Ball (jmp_buf buf, I)** : Return to the place indicated by buf, and return to I. 。

```cpp
// A simple C program to demonstrate working of setjmp() and longjmp()
#include<stdio.h>
#include<setjmp.h>
jmp_buf buf;
void func()
{
    printf("Welcome to GeeksforGeeks\n");

    // Jump to the point setup by setjmp
    longjmp(buf, 1);

    printf("Geek2\n");
}

int main()
{
    // Setup jump position using buf and return 0
    if (setjmp(buf))
        printf("Geek3\n");
    else
    {
        printf("Geek4\n");
        func();
    }
    return 0;
}
```

输出:

```cpp
Geek4
Welcome to GeeksforGeeks
Geek3
```

这些函数的主要特点是提供了一种偏离标准调用和返回顺序的方式。这主要是用来在 C 中实现异常处理的 **setjmp** 可以像 **try** 一样使用(在 C++ 和 Java 这样的语言中)。对**longmp**的调用可以像**抛出**一样使用(注意 longmp()将控制转移到 setjmp()设置的点)。

本文由**阿迪亚查特吉**供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论