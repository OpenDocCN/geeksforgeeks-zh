# 为什么 C 语言需要严格的混叠？

> 原文:[https://www.geeksforgeeks.org/strict-aliasing-required-c/](https://www.geeksforgeeks.org/strict-aliasing-required-c/)

考虑下面的 C 程序。

```cpp
// A C program to demonstrate need of strict 
// aliasing
#include<stdio.h>

// Value of 'a' can be accessed/modified either
// through 'a' or through 'b'
int a = 5;
int* b = &a;

int func(double* b)
{
    a = 1;

    // The below statement modifies 'a'
    *b = 5.10;

    return (a);
}

int main()
{
    printf("%d", func((double*)&a));
    return 0;
}
```

输出:

```cpp
1717986918
```

如果我们称之为**“func()”**，它将返回常量 1。但是也可以将该函数称为**“func((double *)&a)”**，该函数应该返回 1，但返回其他内容。代码只返回常量 1！这是一个大问题，但是**严格别名**解决了这个问题。

**解决方案:**
使用 **[限定限定词](https://www.geeksforgeeks.org/restrict-keyword-c/)** 关键字。这意味着你向编译器保证某个东西没有被指针 restrict 关键字混淆。如果你违背诺言，你只会受苦。详见 C 中[限制关键字。](https://www.geeksforgeeks.org/restrict-keyword-c/)