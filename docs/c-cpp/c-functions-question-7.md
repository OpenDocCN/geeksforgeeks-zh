# C |功能|问题 7

> 原文:[https://www.geeksforgeeks.org/c-functions-question-7/](https://www.geeksforgeeks.org/c-functions-question-7/)

预测产量？

```cpp
#include <stdio.h>
int main()
{
    void demo();
    void (*fun)();
    fun = demo;
    (*fun)();
    fun();
    return 0;
}

void demo()
{
    printf("GeeksQuiz ");
}
```

**(A)** 极客 sQuiz
**(B)** 极客 sQuiz
**(C)** 编译器错误
**(D)** 空白屏幕

**答案:****(B)**

**解释:**这是一个带有函数指针的简单程序。乐趣是指演示。所以这两种说法”(* fun)()；”和“fun()”；意思是一样的。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)