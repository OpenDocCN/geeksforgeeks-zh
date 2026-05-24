# 用例子

在 C 中的 ftell()

> 原文:[https://www.geeksforgeeks.org/ftell-c-example/](https://www.geeksforgeeks.org/ftell-c-example/)

C 语言中的 ftell()用于找出文件指针在文件中相对于文件开始的位置。ftell()的语法是:

```cpp
long ftell(FILE *pointer)

```

考虑下面的 C 程序。示例中拍摄的文件包含以下数据:
“那边有人在叫你。我们要去上班了。照顾好自己。”(不带引号)
当执行 fscanf 语句时，单词“某人”存储在字符串中，指针移动到“某人”之外。因此，当“某人”的长度为 6 时，ftell(fp)返回 7。

```cpp
// C program to demonstrate use of ftel()                                
#include<stdio.h>

int main()
{
    /* Opening file in read mode */
    FILE *fp = fopen("test.txt","r");

    /* Reading first string */
    char string[20];   
    fscanf(fp,"%s",string);

    /* Printing position of file pointer */
    printf("%ld", ftell(fp));
    return 0;
}
```

输出:假设 test.txt 包含“那边有人…”。

```cpp
7

```

本文由 **Hardik Gaur** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。