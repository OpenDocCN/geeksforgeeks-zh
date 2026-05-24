# C 程序打印字符串，程序中没有任何引号(单引号或双引号)

> 原文:[https://www . geesforgeks . org/c-program-print-string-不带引号-sing-double-program/](https://www.geeksforgeeks.org/c-program-print-string-without-quote-singe-double-program/)

使用 C 或 C++ 在程序中的任何地方打印字符串而不使用引号。
注意:不应从控制台读取输入。

思路是在 C 中使用[宏处理器(参考本文第 6 点)。传递给宏的标记可以通过在它前面使用#转换为字符串。](https://www.geeksforgeeks.org/interesting-facts-preprocessors-c/)

```cpp
// C program to print a string without 
// quote in the program
#include <stdio.h>
#define get(x) #x
int main()
{
    printf(get(vignesh));
    return 0;
}
```

输出:

```cpp
vignesh

```

本文由 **Vignesh** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。