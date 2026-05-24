# C 语言中的 scanf()和 fscanf()简单而强大

> 原文:[https://www . geeksforgeeks . org/scanf-and-fscanf-in-c-simple-然而-powerive/](https://www.geeksforgeeks.org/scanf-and-fscanf-in-c-simple-yet-poweful/)

我们很多人都知道 scanf 的传统用法。以下是一些鲜为人知的事实

如何只读取一部分我们需要的输入？例如，考虑一些只包含后跟整数或浮点数的字符的输入流。我们只需要扫描那个整数或浮点数。

即
输入:“这是数值 100”，
输出:数值读取为 100
输入:“这是数值 21.2”，
输出:数值读取为 21.2

## C

```cpp
/* C program to demonstrate that we can
   ignore some string in scanf() */
#include <stdio.h>
int main()
{
    int a;
    scanf("This is the value %d", &a);
    printf("Input value read : a = %d", a);
    return 0;
}
// Input  : This is the value 100
// Output : Input value read : a = 100
```

现在，假设我们不知道前面的字符是什么，但是我们肯定知道最后一个值是一个整数。如何将最后一个值扫描为整数？

以下解决方案仅在输入字符串没有空格时有效。

## C

```cpp
/* Sample C program to demonstrate use of *s */
#include<stdio.h>
int main()
{
    int a;
    scanf("%*s %d", &a);
    printf("Input value read : a=%d",a);
    return 0;
}

// Input: "blablabla 25"
// Output: Value read : 25
```

**说明**:scanf 中的%*s 用于根据需要忽略一些输入。在这种情况下，它会忽略输入，直到下一个空格或换行符。同样，如果你写%*d，它将忽略整数，直到下一个空格或换行符。

乍一看，上述事实似乎不是一个有用的技巧。为了理解它的用法，我们先来看看 fscanf()。

**fscanf():** 厌倦了所有从文件中读取的笨拙语法？嗯，fscanf 来救援了。

```cpp
int fscanf(FILE *ptr, const char *format, ...) 
```

fscanf 从 file 指针(ptr)指向的文件中读取，而不是从输入流中读取。

考虑以下文本文件 abc.txt

```cpp
NAME    AGE   CITY
abc     12    hyderbad
bef     25    delhi
cce     65    bangalore  
```

现在，我们只想读取上述文本文件的城市字段，而忽略所有其他字段。fscanf 和上面提到的技巧相结合可以轻松做到这一点

## C

```cpp
/*c program demonstrating fscanf and its usage*/
#include<stdio.h>
int main()
{
    FILE* ptr = fopen("abc.txt","r");
    if (ptr==NULL)
    {
        printf("no such file.");
        return 0;
    }

    /* Assuming that abc.txt has content in below
       format
       NAME    AGE   CITY
       abc     12    hyderbad
       bef     25    delhi
       cce     65    bangalore */
    char buf[100];
    while (fscanf(ptr,"%*s %*s %s ",buf)==1)
        printf("%s\n", buf);

    return 0;
}
```

**输出:**

```cpp
CITY
hyderbad
delhi
bangalore 
```

**练习:**使用 fscanf 统计文件中的单词、字符和行数！

本文由 Nikhil Chakravartula 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。