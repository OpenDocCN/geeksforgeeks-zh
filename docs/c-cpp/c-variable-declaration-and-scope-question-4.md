# C |变量声明和范围|问题 4

> 原文:[https://www . geesforgeks . org/c-variable-declaration-and-scope-question-4/](https://www.geeksforgeeks.org/c-variable-declaration-and-scope-question-4/)

```cpp
#include <stdio.h>
extern int var = 0;
int main()
{
    var = 10;
    printf("%d ", var);
    return 0;
}
```

**(A)** 10
**(B)** 编译器错误:var 未定义
**(C)**0

**答案:****(A)**

**解释:**如果只声明了一个变量，并且初始化器也提供了该声明，那么该变量的内存将被分配，即该变量将被视为已定义。

参考:[理解 C](https://www.geeksforgeeks.org/understanding-extern-keyword-in-c/)

[中的“extern”关键字本题竞猜](https://www.geeksforgeeks.org/quiz-corner-gq/)