# C |循环&控制结构|问题 4

> 原文:[https://www . geesforgeks . org/c-loops-control-structure-question-4/](https://www.geeksforgeeks.org/c-loops-control-structure-question-4/)

```cpp
#include <stdio.h>
int main()
{
    int i = 3;
    switch (i)
    {
        case 0+1: printf("Geeks");
                break;
        case 1+2: printf("Quiz");
                break;
        default: printf("GeeksQuiz");
    }
    return 0;
}
```

以上程序的输出是什么？
**(A)** 极客
**(B)** 测验
**(C)** 极客 sQuiz
**(D)** 编译时错误

**答案:****(B)**

**解释:**表达式在案例中得到评估。评估 **1+2 = 3** 并打印**测验**后，控制转到第二个案例块。