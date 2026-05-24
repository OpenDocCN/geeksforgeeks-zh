# C |字符串|问题 12

> 原文:[https://www.geeksforgeeks.org/c-string-question-12/](https://www.geeksforgeeks.org/c-string-question-12/)

以下程序的输出

```cpp
#include <stdio.h>
int fun(char *p)
{
    if (p == NULL || *p == '\0') return 0;
    int current = 1, i = 1;
    while (*(p+current))
    {
        if (p[current] != p[current-1])
        {
            p[i] = p[current];
            i++ ;
        }
        current++ ;
    }
    *(p+i)='\0';
    return i;
}

int main()
{
    char str[] = "geeksskeeg";
    fun(str);
    puts(str);
    return 0;
}
```

**(A)**geks 小桶
**(B)**geeks keeg
**(C)**geeks
**(D)**垃圾值

**答案:****(A)**

**解释:**该功能主要是将一个字符连续出现一次以上替换为一次出现。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)