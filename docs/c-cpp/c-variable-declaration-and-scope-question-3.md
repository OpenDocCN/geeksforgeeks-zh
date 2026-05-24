# C |变量声明和范围|问题 3

> 原文:[https://www . geesforgeks . org/c-variable-declaration-and-scope-question-3/](https://www.geeksforgeeks.org/c-variable-declaration-and-scope-question-3/)

```cpp
#include <stdio.h>
extern int var;
int main()
{
    var = 10;
    printf("%d ", var);
    return 0;
}
```

**(A)** 编译器错误:var 未定义
**(B)**20
**(C)**0

**答案:****(A)**

**说明:** var 仅声明未定义(未分配内存)

参考:[理解 C](https://www.geeksforgeeks.org/understanding-extern-keyword-in-c/)

[中“extern”关键字本题](https://www.geeksforgeeks.org/quiz-corner-gq/)小测验