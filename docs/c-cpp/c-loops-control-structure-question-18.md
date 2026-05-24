# C |循环&控制结构|问题 18

> 原文:[https://www . geesforgeks . org/c-loops-control-structure-question-18/](https://www.geeksforgeeks.org/c-loops-control-structure-question-18/)

极客 sQuiz 被打印了多少次

```cpp
#include<stdio.h>
int main()
{
    int i = -5;
    while (i <= 5)
    {
        if (i >= 0)
            break;
        else
        {
            i++ ;
            continue;
        }
        printf("GeeksQuiz");
    }
    return 0;
}
```

**(A)** 10 次
**(B)** 5 次
**(C)** 无限次
**(D)** 0 次

**答案:****(D)**

**解释:**循环在小于 0 的同时不断递增 I。当我变成 0 时，循环中断。所以极客 sQuiz 根本就不印刷。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)