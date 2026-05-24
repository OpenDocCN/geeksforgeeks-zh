# C |循环&控制结构|问题 20

> 原文:[https://www . geesforgeks . org/c-loops-control-structure-question-20/](https://www.geeksforgeeks.org/c-loops-control-structure-question-20/)

```cpp
#include <stdio.h>
int main()
{
    int x = 3;
    if (x == 2); x = 0;
    if (x == 3) x++ ;
    else x += 2;

    printf("x = %d", x);

    return 0;
}
```

**(A)**x = 4
**(B)**x = 2
**(C)**编译器错误
**(D)**x = 0

**答案:****(B)**

**解释:**x 的值应为 2。注意第一个 if 语句后的分号。x 在第一个 if 语句后变成 0。所以控制转到第二个 if else 语句的 else 部分。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)