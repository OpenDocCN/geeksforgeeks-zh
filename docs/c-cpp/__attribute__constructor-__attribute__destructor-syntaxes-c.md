# __ 属性 __((构造函数))和 _ _ 属性 _ _((析构函数))C

中的语法

> 原文:[https://www . geesforgeks . org/_ _ attribute _ _ constructor-_ _ attribute _ _ destructor-syntax-c/](https://www.geeksforgeeks.org/__attribute__constructor-__attribute__destructor-syntaxes-c/)

用 GCC 编译器用 C 写两个函数，一个在主函数之前执行，一个在主函数之后执行。

**GCC 特定语法**:

1. **__attribute__((构造函数))**语法:这种特殊的 GCC 语法在与函数一起使用时，在程序启动时，即在 **main()** 函数之前执行相同的函数。

2. **__attribute__((析构函数))**语法:这种特殊的 GCC 语法与函数一起使用时，在程序通过 _exit 终止之前，即在 **main()** 函数之后，执行相同的函数。

**解释** :
构造函数和析构函数的工作方式是共享对象文件包含特殊的节(。演员和。包含对分别用构造函数和析构函数属性标记的函数的引用。当库被加载/卸载时，动态加载程序检查这些部分是否存在，如果存在，则调用其中引用的函数。

关于这些值得注意的几点:
1。 **__attribute__((构造函数))**在加载共享库时运行，通常是在程序启动期间。
2。 **__attribute__((析构函数))**在卸载共享库时运行，通常是在程序退出时。
3。这两个括号大概是为了将它们与函数调用区分开来。
4。**_ _ 属性 __** 是 GCC 特有的语法；不是函数或宏。

**驾驶员代码**:

```cpp
// C program to demonstrate working of
// __attribute__((constructor)) and
// __attribute__((destructor))
#include<stdio.h>

// Assigning functions to be executed before and
// after main()
void __attribute__((constructor)) calledFirst();
void __attribute__((destructor)) calledLast();

void main()
{
    printf("\nI am in main");
}

// This function is assigned to execute before
// main using __attribute__((constructor))
void calledFirst()
{
    printf("\nI am called first");
}

// This function is assigned to execute after
// main using __attribute__((destructor))
void calledLast()
{
    printf("\nI am called last");
}
```

输出:

```cpp
I am called first
I am in main
I am called last

```

本文由**里沙夫·拉吉**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。