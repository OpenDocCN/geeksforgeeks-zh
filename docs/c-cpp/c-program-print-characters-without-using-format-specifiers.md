# 不使用格式说明符打印字符的 C 程序

> 原文:[https://www . geesforgeks . org/c-program-print-characters-不带格式说明符/](https://www.geeksforgeeks.org/c-program-print-characters-without-using-format-specifiers/)

众所周知，C 语言中有各种 [**格式说明符**](https://www.geeksforgeeks.org/data-types-in-c/) 如%d、%f、%c 等，帮助我们打印字符或其他数据类型。我们通常使用这些说明符和 **printf()** 函数来打印任何变量。但是也有一种方法可以在不使用%c 格式说明符的情况下打印字符。这可以通过使用下面显示的方法获取任何特定字符的任何 ASCII 码的字符值来获得。
示例:

```cpp
// Prints characters without format specifiers
#include <stdio.h>

int main()
{
    printf("\x47 \n");
    printf("\x45 \n");
    printf("\x45 \n");
    printf("\x4b \n");
    printf("\x53");
    return 0;
}
```

输出:

```cpp
G 
E 
E 
K 
S

```

本文由 [**【钦莫伊蕾恩卡】**](https://www.linkedin.com/in/lenkachinmoy/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。