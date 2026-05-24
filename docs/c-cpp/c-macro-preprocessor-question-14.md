# C |宏&预处理器|第 14 题

> 原文:[https://www . geesforgeks . org/c-宏-预处理器-问题-14/](https://www.geeksforgeeks.org/c-macro-preprocessor-question-14/)

```cpp
#include <stdio.h>
#define get(s) #s

int main()
{
    char str[] = get(GeeksQuiz);
    printf("%s", str);
    return 0;
}
```

**(A)** 编译器错误
**(B)**# GeeksQuiz
**(C)**GeeksQuiz
**(D)**ggeeksquick

**答案:****(C)**
**解释:**预处理运算符“#”用于将字符串参数转换为字符串常量。

[本题小考](http://quiz.geeksforgeeks.org/macro-preprocessor/)