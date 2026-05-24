# C | Misc |问题 9

> 原文:[https://www.geeksforgeeks.org/c-misc-question-9/](https://www.geeksforgeeks.org/c-misc-question-9/)

```cpp
#include <stdio.h>
#include <string.h>
int main()
{
    char a[] = {'G','E','E','K','S','Q','U','I','Z'};
    char b[] = "QUIZ";
    char c[] = "GEEKS";
    char d[] = "1234";
    int l = strlen(a);
    int o = printf("%d", sizeof((sizeof(l)+(c[5]+d[0]+a[1]+b[2]))) );
    printf("%c", a[o]);
    return 0;
}
```

感谢 Gokul 贡献这个问题。
**(A)**【4E】
**(B)**8E
**(C)**1234 q
**(D)**编译器依赖

**答案:** **(D)**

解释:输出似乎是编译器依赖。这取决于 size of 的返回类型的大小。sizeof 的返回类型是 std::size_t。在某些编译器中，size_t 的大小是 4 个字节，在另一些编译器中是 8 个字节。

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/misc-gq/)