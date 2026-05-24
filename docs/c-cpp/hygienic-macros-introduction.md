# 卫生宏:简介

> 原文:[https://www.geeksforgeeks.org/hygienic-macros-introduction/](https://www.geeksforgeeks.org/hygienic-macros-introduction/)

我们都很熟悉像 c 语言中[宏](https://www.geeksforgeeks.org/interesting-facts-preprocessors-c/)的工作方式，在某些情况下，宏扩展会因为意外捕获标识符而导致不良结果。
例如:

```cpp
// C program to illustrate a situation known as 
// accidental capture of identifiers - an
// undesirable result caused by unhygienic macros
#define INCI(i) do { int x = 0; ++ i; } while(0)
int main(void)
{
    int x = 4, y = 8;

    // macro called first time
    INCI(x);

    // macro called second time
    INCI(y);

    printf("x = %d, b = %d\n", x, y);
    return 0;
}
```

该代码实际上相当于:

```cpp
// C program to illustrate unhygenic macros
// with Macro definition substituted in source code.
int main(void)
{
    int x = 4, y = 8;

    //macro called first time
    do { int x = 0; ++ x; } while(0);

    //macro called second time
    do { int x = 0; ++ y; } while(0);

    printf("x = %d, b = %d\n", x, y);
    return 0;
}
```

输出:

```cpp
x = 4, y = 9

```

在主函数范围内声明的变量 a 被宏定义中的变量 a 掩盖，因此 **a = 4** 永远不会被更新(称为意外捕获)。

**卫生宏**

卫生宏是这样的宏，它的扩展保证不会导致标识符的意外捕获。一个健康的宏不会使用可能会干扰扩展中的代码的变量名。
只需在宏定义中更改变量的名称，就可以避免上述代码中的情况，这将产生不同的输出。

```cpp
// C program to illustrate  
// Hygienic macros using 
// identifier names such that 
// they do not cause 
// the accidental capture of identifiers
#define INCI(i) do { int m = 0; ++ i; } while(0)
int main(void)
{
    int x = 4, y = 8;

    // macro called first time
    INCI(x);

    // macro called second time
    INCI(y);

    printf("x = %d, y = %d\n", x, y);
    return 0;
}
```

输出:

```cpp
x = 5, y = 9

```

本文由 [Palash Nigam](https://www.hackerearth.com/@palash40) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。