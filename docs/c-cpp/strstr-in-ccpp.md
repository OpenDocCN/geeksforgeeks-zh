# C/c++

中的 strstr()

> 原文:[https://www.geeksforgeeks.org/strstr-in-ccpp/](https://www.geeksforgeeks.org/strstr-in-ccpp/)

在 C++ 中，STD::strtr()是用于字符串处理的预定义函数。 **string.h** 是字符串函数所需的头文件。

该函数以两个字符串 **s1** 和 **s2** 为自变量，找到子字符串 **s2** 在字符串 **s1** 中的第一次出现。匹配过程不包括终止的空字符(“\0”)，但函数就此结束。

**语法:**

```cpp
char *strstr (const char *s1, const char *s2);

Parameters:
s1: This is the main string to be examined.
s2: This is the sub-string to be searched in *s1* string.

```

**返回值:**该函数返回指向在 *s1* 中找到的 *s2* 的第一个字符的指针，否则如果 *s2* 在 *s1* 中不存在，则返回空指针。如果 s2 指向空字符串，则返回 s1。

**示例:**

```cpp
// CPP program to illustrate strstr()
#include <string.h>
#include <stdio.h>

int main()
{
    // Take any two strings
    char s1[] = "GeeksforGeeks";
    char s2[] = "for";
    char* p;

    // Find first occurrence of s2 in s1
    p = strstr(s1, s2);

    // Prints the result
    if (p) {
        printf("String found\n");
        printf("First occurrence of string '%s' in '%s' is '%s'", s2, s1, p);
    } else
        printf("String not found\n");

    return 0;
}
```

输出:

```cpp
String found
First occurrence of string 'for' in 'GeeksforGeeks' is 'forGeeks'

```

**应用:将一个字符串替换为另一个**
在本例中，借助 strstr()函数，我们首先在 **s1** 中搜索 *STL* 子字符串的出现，然后将该单词替换为 *Strings* 。

```cpp
// CPP program to illustrate strstr()
#include <string.h>
#include <stdio.h>

int main()
{
    // Take any two strings
    char s1[] = "Fun with STL";
    char s2[] = "STL";
    char* p;

    // Find first occurrence of s2 in s1
    p = strstr(s1, s2);

    // Prints the result
    if (p) {
        strcpy(p, "Strings");
        printf("%s", s1);
    } else
        printf("String not found\n");

    return 0;
}
```

输出:

```cpp
Fun with Strings

```

本文由阿卡什·古普塔供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。