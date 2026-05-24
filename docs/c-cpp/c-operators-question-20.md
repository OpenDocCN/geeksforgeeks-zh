# C |操作员|第 27 题

> 原文:[https://www.geeksforgeeks.org/c-operators-question-20/](https://www.geeksforgeeks.org/c-operators-question-20/)

预测以下 C 程序的输出

```cpp
#include <stdio.h>
int main()
{
    int i = 0;
    do
    {
        printf("GeeqsQuiz ");
        i = i++ ;
    }
    while (i < 5);
    return 0;
}
```

**(A)**geesquick geesquick geesquick geesquick
**(B)**无限时间 geesquiz
**(C)**未定义行为

**答案:****(C)**

**解释:**以下语句导致未定义行为。

```cpp
 i = i++ ;

```

详见[https://www.geeksforgeeks.org/sequence-points-in-c-set-1/](https://www.geeksforgeeks.org/sequence-points-in-c-set-1/)。

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/operators-gq/)