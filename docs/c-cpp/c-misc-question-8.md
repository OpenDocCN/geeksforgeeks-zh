# C | Misc |问题 8

> 原文:[https://www.geeksforgeeks.org/c-misc-question-8/](https://www.geeksforgeeks.org/c-misc-question-8/)

C 以下代码的输出？假设 int 需要 4 个字节。

```cpp
#include<stdio.h>
int x = 5;
int main()
{
    int arr[x];
    static int x = 0;
    x = sizeof(arr);
    printf("%d", x<<2);
    return 0;
}
```

感谢 Gokul Kumar 贡献了这个问题。
**(A)** 第行编译器错误“静态 int x = 0”
**(B)**7
**(C)**80
**(D)**20

**答案:****(C)**

**解释:**的大小给出 arr * int 的大小，以字节为单位= 20
左移

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/misc-gq/)