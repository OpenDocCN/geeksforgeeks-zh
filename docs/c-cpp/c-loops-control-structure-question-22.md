# C | Misc |问题 7

> 原文:[https://www . geesforgeks . org/c-loops-control-structure-question-22/](https://www.geeksforgeeks.org/c-loops-control-structure-question-22/)

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

[本题小测验](https://www.geeksforgeeks.org/c-language-2-gq/misc-gq/)