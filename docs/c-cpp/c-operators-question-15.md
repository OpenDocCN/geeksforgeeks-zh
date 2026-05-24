# C |操作员|第 15 题

> 原文:[https://www.geeksforgeeks.org/c-operators-question-15/](https://www.geeksforgeeks.org/c-operators-question-15/)

预测后续程序的输出。假设字符使用 ASCII 值表示。

```cpp
#include <stdio.h>
#define VAL 32

int main()
{
    char arr[] = "geeksquiz";
    *(arr + 0) &= ~VAL;
    *(arr + 5) &= ~VAL;
    printf("%s", arr);

    return 0;
}
```

**(A)** 极客 sQuiz
**(B)** 极客 sQuiz
**(C)** 极客 squiz
**(D)** 极客 squiz
**(E)** 垃圾 eeks 垃圾 uiz

**答案:****(A)**

**解释:**问题的关键在于
此语句从小写字符的 ascii 值中减去 32，从而将其转换为大写。这是将字母表转换为大写字母的另一种方法，方法是重置位于值 32 的位，即从 LSB 开始的第 5 位(假设 LSB 位位于位置 0)。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)