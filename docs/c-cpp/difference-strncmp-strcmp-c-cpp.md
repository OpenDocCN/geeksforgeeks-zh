# C/c++ 中 strncmp()和 strcmp 的区别

> 原文:[https://www . geesforgeks . org/difference-strncmp-str CMP-c-CPP/](https://www.geeksforgeeks.org/difference-strncmp-strcmp-c-cpp/)

先决条件: [strncmp](https://www.geeksforgeeks.org/stdstrncmp-in-c/) 、 [strcmp](https://www.geeksforgeeks.org/strcmp-in-c-cpp/)

这两者的基本区别是:

1.  strcmp 比较两个字符串，直到任何一个字符串的空字符出现，而 strncmp 最多比较两个字符串的 **num** 个字符。但是如果*数*等于任意一根绳子的长度，那么 *strncmp* 的行为类似于 *strcmp* 。
2.  *strcmp* 函数的问题是，如果参数中传递的两个字符串都没有以空字符结束，那么字符的比较将继续，直到系统崩溃。但是通过 *strncmp* 功能，我们可以限制与 **num** 参数的比较。

当将 str1 和 str2 作为参数传递给 **strcmp()** 函数时，它会逐个字符比较这两个字符串，直到出现空字符(' \0 ')。在我们的例子中，高达字符【T2 的】的两个字符串保持不变，但是在此之后 **str1** 的字符**【h】**的 ASCII 值为 104，而 **str2** 的空字符**的 ASCII 值为 0。由于 str1 字符的 ASCII 值大于 str2 字符的 ASCII 值，因此 *strcmp()* 函数返回大于零的值。因此，在 strcmp()函数中，字符串 str1 大于字符串 str2。
当在 **strncmp()** 函数中传递这些参数时，第三个参数**num**up 想要比较字符串，然后它逐个字符地比较字符串直到 num(如果 num < =最小字符串的长度)或者直到最小字符串的 null 字符。在我们的例子中，两个字符串都有相同的字符直到 *num* ，所以 *strncmp()* 函数返回值零。因此，在 strncmp()函数中，字符串 str1 等于字符串 str2。**

```cpp
// C, C++ program demonstrate difference between
// strncmp() and strcmp()
#include <stdio.h>
#include <string.h>

int main()
{
    // Take any two strings
    char str1[] = "akash";
    char str2[] = "akas";

    // Compare strings using strncmp()
    int result1 = strncmp(str1, str2, 4);

    // Compare strings using strcmp()
    int result2 = strcmp(str1, str2);

    // num is the 3rd parameter of strncmp() function 
    if (result1 == 0)         
        printf("str1 is equal to str2 upto num characters\n");    
    else if (result1 > 0)
        printf("str1 is greater than str2\n");
    else
        printf("str2 is greater than str1\n");

    printf("Value returned by strncmp() is: %d\n", result1);

    if (result2 == 0) 
        printf("str1 is equal to str2\n");    
    else if (result2 > 0)
        printf("str1 is greater than str2\n");
    else
        printf("str2 is greater than str1\n");

    printf("Value returned by strcmp() is: %d", result2);

    return 0;
}
```

输出:

```cpp
str1 is equal to str2 upto num characters
Value returned by strncmp() is: 0
str1 is greater than str2
Value returned by strcmp() is: 104

```

本文由**阿卡什·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。