# C |循环&控制结构|问题 16

> 原文:[https://www . geesforgeks . org/c-loops-control-structure-question-16/](https://www.geeksforgeeks.org/c-loops-control-structure-question-16/)

以下程序的输出是什么？

```cpp
#include <stdio.h>
int main()
{
    char check = 'a';
    switch (check)
    {
        case 'a' || 1: printf("Geeks ");

        case 'b' || 2: printf("Quiz ");
                    break;
        default: printf("GeeksQuiz");
    }
    return 0;
}
```

**(A)** 极客
**(B)** 极客测验
**(C)** 极客测验极客 sQuiz
**(D)** 编译时错误

**答案:****(D)**

**解释:**一个表达式在一个案例标签中得到评估。使用的两种情况都被评估为 1(真)。所以*编译时错误:重复的事例值*被闪为不允许重复的事例。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)