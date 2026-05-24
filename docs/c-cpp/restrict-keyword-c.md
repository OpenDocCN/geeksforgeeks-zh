# 限制 C 中的关键字

> 原文:[https://www.geeksforgeeks.org/restrict-keyword-c/](https://www.geeksforgeeks.org/restrict-keyword-c/)

在 [C 编程语言](https://www.geeksforgeeks.org/c/)(99 标准之后)中，引入了一个新的关键字，称为 restrict。

*   restrict 关键字主要在指针声明中用作指针的类型限定符。
*   它没有添加任何新功能。这只是程序员告知编译器可以进行的优化的一种方式。
*   当我们对指针 ptr 使用 restrict 时，它告诉编译器 ptr 是访问它所指向的对象的唯一方法，换句话说，没有其他指针指向同一个对象，即 restrict 关键字指定特定的指针参数不别名任何其他参数，编译器不需要添加任何额外的检查。
*   如果程序员使用了 restrict 关键字并违反了上述条件，那么结果就是未定义的行为。
*   C++ 不支持 restrict。这是一个只有 C 的关键字。

## C

```cpp
// C program to use restrict keyword.
#include <stdio.h>

// Note that the purpose of restrict is to
// show only syntax. It doesn't change anything
// in output (or logic). It is just a way for
// programmer to tell compiler about an
// optimization
void use(int* a, int* b, int* restrict c)
{
    *a += *c;

    // Since c is restrict, compiler will
    // not reload value at address c in
    // its assembly code. Therefore generated
    // assembly code is optimized
    *b += *c; 
}

int main(void)
{
    int a = 50, b = 60, c = 70;
    use(&a, &b, &c);
    printf("%d %d %d", a, b, c);
    return 0;
}
```

输出:

```cpp
120 130 70
```

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。