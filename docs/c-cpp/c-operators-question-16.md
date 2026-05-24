# C |操作员|第 16 题

> 原文:[https://www.geeksforgeeks.org/c-operators-question-16/](https://www.geeksforgeeks.org/c-operators-question-16/)

预测以下程序的输出:

```cpp
#include <stdio.h>
int main()
{
    printf("%d", 1 << 2 + 3 << 4);
    return 0;
}
```

**(A)**112
**(B)**52
**(C)**512
**(D)**0

**答案:****(C)**

**说明:**程序背后的主要逻辑是运算符的[优先顺序](http://en.wikipedia.org/wiki/Operators_in_C_and_C%2B%2B#Operator_precedence)和结合度。加法(+)运算符的优先级高于移位(< <)运算符。所以，这个表达式可以归结为*1<<(2+3)<<4*，而后者又可以归结为(1 < < 5) < < 4，因为换挡操作符具有从左到右的关联性。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)