# C |高级指针|问题 7

> 原文:[https://www.geeksforgeeks.org/c-arrays-question-14/](https://www.geeksforgeeks.org/c-arrays-question-14/)

假设 int 的大小是 4。

```cpp
#include <stdio.h>
void f(char**);
int main()
{
    char *argv[] = { "ab", "cd", "ef", "gh", "ij", "kl" };
    f(argv);
    return 0;
}
void f(char **p)
{
    char *t;
    t = (p += sizeof(int))[-1];
    printf("%s\n", t);
}
```

**(A)**ab
**(B)**CD
**(C)**ef
**(D)**GH

**答案:****(D)**

**解释:**表达式(p += sizeof(int))[-1]可以写成(p += 4)[-1]可以写成

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/advanced-pointer-c-gq/)