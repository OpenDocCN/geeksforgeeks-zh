# 多行 C/C++ 怎么写长串？

> 原文:[https://www . geesforgeks . org/如何编写多行长字符串-cc/](https://www.geeksforgeeks.org/how-to-write-long-strings-in-multi-lines-cc/)

想象一个我们想用 C 或 C++ 使用或打印一个很长很长的字符串的情况，怎么做？

在 C/C++ 中，我们可以使用中间的两个双引号在中间的任意点断开一个字符串。下面是一个简单的例子来证明这一点。

```cpp
#include<stdio.h>
int main()
{
   // We can put two double quotes anywhere in a string
   char *str1  = "geeks""quiz"; 

   // We can put space line break between two double quotes
   char *str2  = "Qeeks"     "Quiz";
   char *str3  = "Qeeks"     
                 "Quiz";

   puts(str1);
   puts(str2);
   puts(str3);

   puts("Geeks"        // Breaking string in multiple lines
        "forGeeks");
   return 0;
}
```

输出:
*【geeksquiz】
【qeksquiz】
【qeeksquiz】
【geeksforgeeks】*

下面是几个例子，为了更好的可读性，使用两个双引号将长字符串断开。

```cpp
#include<stdio.h>
int main()
{
   char *str = "These are reserved words in C language are int, float, "
               "if, else, for, while etc. An Identifier is a sequence of"
               "letters and digits, but must start with a letter. "
               "Underscore ( _ ) is treated as a letter. Identifiers are "
               "case sensitive. Identifiers are used to name variables,"
               "functions etc.";
   puts(str);
   return 0; 
} 
```

输出:*这些是 C 语言中的保留字，有 int、float、if、else、for、while 等。标识符是字母和数字的序列，但必须以字母开头。下划线(_)被视为字母。标识符区分大小写。标识符用于命名变量、函数等。*

同样，我们可以在 printf 和或 cout 中编写长字符串。

```cpp
#include<stdio.h>
int main()
{
   char *str = "An Identifier is a sequence of"
               "letters and digits, but must start with a letter. "
               "Underscore ( _ ) is treated as a letter. Identifiers are "
               "case sensitive. Identifiers are used to name variables,"
               "functions etc.";
   printf ("These are reserved words in C language are int, float, "
            "if, else, for, while etc. %s ", str);
   return 0; 
}
```

输出:*这些是 C 语言中的保留字，有 int、float、if、else、for、while 等。标识符是字母和数字的序列，但必须以字母开头。下划线(_)被视为字母。标识符区分大小写。标识符用于命名变量、函数等。*

本文由 **Ayush Jain** 供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论