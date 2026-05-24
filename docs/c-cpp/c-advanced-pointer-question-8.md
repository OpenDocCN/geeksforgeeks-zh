# C |高级指针|问题 8

> 原文:[https://www . geesforgeks . org/c-advanced-pointer-question-8/](https://www.geeksforgeeks.org/c-advanced-pointer-question-8/)

```cpp
#include <stdio.h>
int main()
{
    int a[][3] = {1, 2, 3, 4, 5, 6};
    int (*ptr)[3] = a;
    printf("%d %d ", (*ptr)[1], (*ptr)[2]);
    ++ ptr;
    printf("%d %d\n", (*ptr)[1], (*ptr)[2]);
    return 0;
}

```

**(A)**2 3 5 6
**(B)**2 3 4 5
**(C)**4 5 0 0
**(D)**以上都不是

**答案:****(A)**

**说明:**

[本题小测验](https://www.geeksforgeeks.org/c-language-2-gq/advanced-pointer-c-gq/)