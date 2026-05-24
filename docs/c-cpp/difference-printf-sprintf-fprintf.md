# printf、sprintf、fprintf 有什么区别？

> 原文:[https://www . geesforgeks . org/difference-printf-sprintf-fprintf/](https://www.geeksforgeeks.org/difference-printf-sprintf-fprintf/)

<u>**printf:**</u>
printf 功能用于在 stdout 控制台上打印字符流数据。

**语法:**

```cpp
 int printf(const char* str, ...); 
```

**示例:**

```cpp
// simple print on stdout 
#include<stdio.h>
int main()
{
   printf("hello geeksquiz");
   return 0;
}
```

**输出:**

```cpp
 hello geeksquiz
```

<u>**sprintf:**</u>
语法:

```cpp
int sprintf(char *str, const char *string,...); 
```

字符串打印功能，而不是在控制台上打印，将它存储在 sprintf 中指定的字符缓冲区中

**示例:**

```cpp
// Example program to demonstrate sprintf()
#include<stdio.h>
int main()
{
    char buffer[50];
    int a = 10, b = 20, c;
    c = a + b;
    sprintf(buffer, "Sum of %d and %d is %d", a, b, c);

    // The string "sum of 10 and 20 is 30" is stored 
    // into buffer instead of printing on stdout
    printf("%s", buffer);

    return 0;
}
```

**输出:**

```cpp
Sum of 10 and 20 is 30
```

<u>**fprintf:**</u>
fprintf 用于打印文件中的字符串内容，但不在 stdout 控制台上。

```cpp
int fprintf(FILE *fptr, const char *str, ...);
```

**示例:**

```cpp
#include<stdio.h>
int main()
{
    int i, n=2;
    char str[50];

    //open file sample.txt in write mode
    FILE *fptr = fopen("sample.txt", "w");
    if (fptr == NULL)
    {
        printf("Could not open file");
        return 0;
    }

    for (i=0; i<n; i++)
    {
        puts("Enter a name");
        gets(str);
        fprintf(fptr,"%d.%s\n", i, str);
    }
    fclose(fptr);

    return 0;
}
```

```cpp
Input: GeeksforGeeks
       GeeksQuiz
Output :  sample.txt file now having output as 
0\. GeeksforGeeks
1\. GeeksQuiz
```

感谢您的阅读，我将很快更新与 scanf，fscanf，sscanf 保持关注。

本文由 **Vankayala Karunakar** 供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。