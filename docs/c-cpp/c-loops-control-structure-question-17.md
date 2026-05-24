# C |循环&控制结构|问题 17

> 原文:[https://www . geesforgeks . org/c-loops-control-structure-question-17/](https://www.geeksforgeeks.org/c-loops-control-structure-question-17/)

预测以下程序的输出:

```cpp
#include <stdio.h>
int main()
{
    int check = 20, arr[] = {10, 20, 30};
    switch (check)
    {
        case arr[0]: printf("Geeks ");
        case arr[1]: printf("Quiz ");
        case arr[2]: printf("GeeksQuiz");
    }
    return 0;
}
```

**(A)** 小考
**(B)** 小考极客 sQuiz
**(C)** 极客 sQuiz
**(D)** 编译时错误

**答案:****(D)**
**解释:**开关块内的事例标签必须是不变的。这就是为什么*编译时错误:大小写标签没有减少到整数常量*会闪烁。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)