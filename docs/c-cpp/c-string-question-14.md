# C |字符串|问题 14

> 原文:[https://www.geeksforgeeks.org/c-string-question-14/](https://www.geeksforgeeks.org/c-string-question-14/)

假设一个字符需要 1 个字节。以下程序的输出？

```cpp
#include<stdio.h>
int main()
{
    char str[20] = "GeeksQuiz";
    printf ("%d", sizeof(str));
    return 0;
}
```

**(A)**9
**(B)**10
**(C)**20
**(D)**垃圾值

**回答:****(C)**

**说明:**注意 sizeof()运算符会返回数组的大小。要获取存储在数组中的字符串的大小，我们需要使用 strlen()。以下程序打印 9。

```cpp
#include <stdio.h>
#include <string.h>
int main()
{
    char str[20] = "GeeksQuiz";
    printf ("%d", strlen(str));
    return 0;
}

```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)