# C |高级指针|问题 4

> 原文:[https://www . geesforgeks . org/c-advanced-pointer-question-4/](https://www.geeksforgeeks.org/c-advanced-pointer-question-4/)

```cpp
#include <stdio.h>

char *c[] = {"GeksQuiz", "MCQ", "TEST", "QUIZ"};
char **cp[] = {c+3, c+2, c+1, c};
char ***cpp = cp;

int main()
{
    printf("%s ", **++ cpp);
    printf("%s ", *--*++ cpp+3);
    printf("%s ", *cpp[-2]+3);
    printf("%s ", cpp[-1][-1]+1);
    return 0;
}
```

**(A)**TEST sQuiz Z CQ
**(B)**MCQ 小考 Z CQ
**(C)** TEST 小考 Z CQ
**(D)***garbage value*sQuiz CQ

**答案:****(A)**
**解释:**让我们先来考虑* *+CPP。[前缀增量和去引用的优先级相同](http://en.cppreference.com/w/cpp/language/operator_precedence)两者的结合性从右向左。所以表达式的求值方式是* *(+++ CPP)。所以 cpp 指向 c+2。所以我们得到“测试”作为输出。注意两次去引用操作符。

同样，你也可以借助[优先表](http://en.cppreference.com/w/cpp/language/operator_precedence)自己尝试其他表达方式。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)