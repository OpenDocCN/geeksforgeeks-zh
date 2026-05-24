# C |变量声明和范围|问题 2

> 原文:[https://www . geeksforgeeks . org/c-变量-声明-范围-问题-2/](https://www.geeksforgeeks.org/c-variable-declaration-and-scope-question-2/)

预测产量

```cpp
#include <stdio.h>
int var = 20;
int main()
{
    int var = var;
    printf("%d ", var);
    return 0;
}
```

**(A)** 垃圾值
**(B)** 20
**(C)** 编译器错误

**答案:****(A)**

**解释:**首先声明 var，然后赋值给它。一旦 var 被声明为局部变量，它就会隐藏全局变量 var。

[本题小测验](https://www.geeksforgeeks.org/quiz-corner-gq/)