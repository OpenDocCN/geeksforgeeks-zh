# C

中的 ispunct()函数

> 原文:[https://www.geeksforgeeks.org/ispunct-function-c/](https://www.geeksforgeeks.org/ispunct-function-c/)

**ispunt()**功能检查一个字符是否是标点符号。
此功能定义的术语“**标点符号**包括所有既不是字母数字也不是空格的可打印字符。例如“@”、“{ content }”；等等。
该功能在 **ctype.h** 头文件中定义。

# 语法:

```cpp
int ispunct(int ch);
ch: character to be checked.
Return Value  : function return nonzero
 if character is a punctuation character;
 otherwise zero is returned. 

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// Program to check punctuation
#include <stdio.h>
#include <ctype.h>
int main()
{
    // The punctuations in str are '!' and ','
    char str[] = "welcome! to GeeksForGeeks, ";

    int i = 0, count = 0;
    while (str[i]) {
        if (ispunct(str[i]))
            count++ ;
        i++ ;
    }
    printf("Sentence contains %d punctuation"
           " characters.\n", count);
    return 0;
}
```

<font size="+1">Output:</font>

```cpp

Sentence contains 2 punctuation characters.

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C program to print all Punctuations
#include <stdio.h>
#include <ctype.h>
int main()
{
    int i;
    printf("All punctuation characters in C"
            " programming are: \n");
    for (i = 0; i <= 255; ++ i)
        if (ispunct(i) != 0)
            printf("%c ", i);
    return 0;
}
```

Output:

```cpp
All punctuation characters in C programming are: 
! " # $ % & ' ( ) * +, - . / : ;  ? @ [ \ ] ^ _ ` { | } ~

```

本文由**Shivani ghishial**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。