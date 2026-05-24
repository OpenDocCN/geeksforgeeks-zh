# C

中的 strpbrk()

> 原文:[https://www.geeksforgeeks.org/strpbrk-in-c/](https://www.geeksforgeeks.org/strpbrk-in-c/)

此函数**查找字符串 s1 中与 s2** 中指定的任何字符匹配的第一个字符(不包括终止空字符)。

```cpp
Syntax : 
char *strpbrk(const char *s1, const char *s2)

Parameters :
s1 : string to be scanned.
s2 : string containing the characters to match.

Return Value :
It returns a pointer to the character in s1 that 
matches one of the characters in s2, else returns NULL.

```

```cpp
// C code to demonstrate the working of
// strpbrk
#include <stdio.h>
#include <string.h>

// Driver function
int main()
{
    // Declaring three strings
    char s1[] = "geeksforgeeks";
    char s2[] = "app";
    char s3[] = "kite";
    char* r, *t;

    // Checks for matching character
    // no match found
    r = strpbrk(s1, s2); 
    if (r != 0)
        printf("First matching character: %c\n", *r);
    else
        printf("Character not found");

    // Checks for matching character
    // first match found at "e"
    t = strpbrk(s1, s3);
    if (t != 0)
        printf("\nFirst matching character: %c\n", *t);
    else
        printf("Character not found");

    return (0);
}
```

输出:

```cpp
Character not found
First matching character: e

```

**实际应用**
这个功能可以用在有带字母串
的人获胜的彩票游戏中，也就是说这个功能可以用在第一个人获胜的任何地方。

```cpp
// C code to demonstrate practical application
// of strpbrk
#include <stdio.h>
#include <string.h>

// Driver function
int main()
{
    // Initializing victory string
    char s1[] = "victory";

    // Declaring lottery strings
    char s2[] = "a23";
    char s3[] = "i22";
    char* r, *t;

    // Use of strpbrk()
    r = strpbrk(s1, s2);
    t = strpbrk(s1, s3);

    // Checks if player 1 has won lottery
    if (r != 0)
        printf("Congrats u have won");
    else
        printf("Better luck next time");

    // Checks if player 2 has won lottery
    if (t != 0)
        printf("\nCongrats u have won");
    else
        printf("Better luck next time");

    return (0);
}
```

输出:

```cpp
Better luck next time
Congrats u have won

```

本文由 **[尚塔努·辛格](https://www.facebook.com/shantanu.singh.3517)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。