# C 中的嵌套函数

> 原文:[https://www.geeksforgeeks.org/nested-functions-c/](https://www.geeksforgeeks.org/nested-functions-c/)

一些程序员认为在另一个函数中定义一个函数被称为“嵌套函数”。但现实是，它不是嵌套函数，它被视为词法范围。词法范围在 C 语言中无效，因为编译器无法到达/找到内部函数的正确内存位置。

C 不支持嵌套函数**，因为我们不能在 C 中定义另一个函数内的函数，我们可以在函数内声明一个函数，但它不是嵌套函数。
因为嵌套函数定义不能[访问周围块的局部变量](https://www.geeksforgeeks.org/g-fact-24/)，所以它们只能访问包含模块的全局变量。这样做是为了全局变量的查找不必通过目录。和 C 语言一样，有两个嵌套的作用域:局部作用域和全局作用域(除此之外，还有内置作用域)。因此，嵌套函数的用途有限。如果我们试图在 C 语言中接近嵌套函数，那么我们会得到编译时错误。**

```cpp
// C program to illustrate the
// concept of Nested function.
#include <stdio.h>
int main(void)
{
    printf("Main");
    int fun()
    {
        printf("fun");

        // defining view() function inside fun() function.
        int view()
        {
            printf("view");
        }
        return 1;
    }
    view();
}
```

**输出:**

```cpp
Compile time error: undefined reference to `view' 
```

**GNU C 编译器的扩展允许嵌套函数的声明。GCC 扩展下嵌套函数的声明需要以 [auto 关键字](https://www.geeksforgeeks.org/type-inference-in-c-auto-and-decltype/)作为前缀/开头。**

```cpp
// C program of nested function
// with the help of gcc extension
#include <stdio.h>
int main(void)
{
    auto int view(); // declare function with auto keyword
    view(); // calling function
    printf("Main\n");

    int view()
    {
        printf("View\n");
        return 1;
    }

    printf("GEEKS");
    return 0;
}
```

**输出:**

```cpp
view
Main
GEEKS 
```

**本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。**

**如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**