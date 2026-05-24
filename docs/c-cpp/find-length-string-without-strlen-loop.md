# 如何在 C 语言中求不带 string.h 和 loop 的字符串的长度？

> 原文:[https://www . geesforgeks . org/find-length-string-不带-strlen-loop/](https://www.geeksforgeeks.org/find-length-string-without-strlen-loop/)

在不使用任何循环和字符串的情况下，找出字符串的长度。

```cpp
Enter a string: GeeksforGeeks (Say user enters GeeksforGeeks)
Entered string is: GeeksforGeeks
Length is: 13

```

您可以假设输入字符串的长度始终小于 100。
以下是解决方案。

## C

```cpp
#include <stdio.h>
int main()
{

    // entered string
    char ch[50] = "GeeksforGeeks";

    // printing entered string
    printf("Entered String is:");

    // returns length of string
    // along printing string
    int len
        = printf("%s\n", ch);

    printf("Length is:");

    // printing length
    printf("%d", len - 1);
}
```

**Output**

```cpp
Entered String is:GeeksforGeeks
Length is:13

```

想法是使用 printf()的返回值。
[printf()返回输出中成功写入的字符数](https://www.geeksforgeeks.org/g-fact-10/)。
在上面的程序中，我们只使用 printf()的属性，因为它返回在数组字符串中输入的字符数。

**另一种不用 string.h 或 loops 来求字符串长度的方法是递归。**
下面的程序使用递归来寻找字符串的长度。

## C

```cpp
// C program for the above approach
#include <stdio.h>

void LengthofString(int n,char *string)
{
    if(string[n] == '\0')
    {
        printf("%i",n);
        return;
    }

    LengthofString(n+1,string);
    //printf("%c",string[n]);
}

int main()
{
    char string[100];
    printf("Give a string : \n");
    scanf("%s",string);
    printf("Entered string is:%s\n", string);
    LengthofString(0,string);

    return 0;
}
```

**Output**

```cpp
Give a string : 
Entered string is:0
1

```

函数 LengthofString 调用自己，直到字符串的字符不是它调用自己的空字符，当它调用自己时，它增加变量“n”的值，该变量存储函数被调用的次数，当它遇到空字符时，函数打印“n”的值，并返回到它被执行的相同方向。
本文由苏米特·辛格·肖汉供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。