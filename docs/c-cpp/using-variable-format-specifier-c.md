# 在 C 语言中使用变量作为格式说明符

> 原文:[https://www . geesforgeks . org/using-variable-format-说明符-c/](https://www.geeksforgeeks.org/using-variable-format-specifier-c/)

众所周知， **printf()** 函数是头文件 **stdio.h** 中 C 编程语言的内置库函数。它用于打印字符、字符串、浮点、整数等。到输出屏幕上。但是，在打印浮点值时，小数点后的位数可以由用户控制。其中一种方法是使用像 **%.2f** 等格式。但是**变量**也可以用于格式化格式说明符。

下面的例子展示了如何做到这一点。

```cpp
// C program to demonstrate use of variable
// in format specifier.
#include <stdio.h>

int main()
{
    float b = 6.412355;

    // using the format specifier %.*f
    // a = 3 will print value of b upto
    // 3 decimal places
    int a = 3;
    printf("%.*f\n", a, b);

    // a = 5 will print value of b upto
    // 3 decimal places
    a = 5;
    printf("%.*f\n", a, b);
    return 0;
}
```

输出:

```cpp
6.412
6.41235

```

本文由 **MAZHAR IMAM KHAN** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。