# C |循环&控制结构|问题 19

> 原文:[https://www . geesforgeks . org/c-loops-control-structure-question-19/](https://www.geeksforgeeks.org/c-loops-control-structure-question-19/)

```cpp
#include <stdio.h>
int main()
{
    int i = 3;
    while (i--)
    {
        int i = 100;
        i--;
        printf("%d ", i);
    }
    return 0;
}
```

**(A)** 无限循环
**(B)**99 99 99
**(C)**99 98 97
**(D)**2 2 2

**回答:****(B)**

**解释:**注意语句中的 I–——而(I–)则改变 main()的 I 更改 while 循环的局部 I。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)