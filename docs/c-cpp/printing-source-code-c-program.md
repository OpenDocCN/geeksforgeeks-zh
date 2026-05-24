# 打印 C 程序本身的源代码

> 原文:[https://www . geesforgeks . org/printing-source-code-c-program/](https://www.geeksforgeeks.org/printing-source-code-c-program/)

如何打印一个 C 程序本身的源代码？注意这和蒯因问题不同。在这里，我们需要修改任何 C 程序，使其打印完整的源代码。

**说明** :
我们可以用文件处理的概念把程序的源代码打印出来作为输出。想法是:显示来自您编写源代码的同一个文件的内容。

C 编程文件的位置包含在预定义的宏 __FILE__ 中。例如:

```cpp

#include <stdio.h>
int main()
{
   // Prints location of C this C code.
   printf("%s",__FILE__);
}
```

上面程序的输出就是这个 C 文件的位置。
以下程序显示这个特定 C 文件的内容(源代码)，因为 __FILE__ 包含这个 C 文件在字符串中的位置。

```cpp

// A C program that prints its source code.
#include <stdio.h>

int main(void)
{
    // We can append this code to any C program
    // such that it prints its source code.

    char c; 
    FILE *fp = fopen(__FILE__, "r");

    do
    {
        c = fgetc(fp);
        putchar(c);
    }
    while (c != EOF);

    fclose(fp);

    return 0;
}
```

**输出**:

```cpp
// A C program that prints its source code.
#include <stdio.h>

int main(void)
{
    // We can append this code to any C program
    // such that it prints its source code.

    char c; 
    FILE *fp = fopen(__FILE__, "r");

    do
    {
        c = fgetc(fp);
        putchar(c);
    }
    while (c != EOF);

    fclose(fp);

    return 0;
}

```

**注意:**由于 fopen 可能被阻止，上述程序可能无法在线编译。

本文由**里沙夫·拉吉**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。