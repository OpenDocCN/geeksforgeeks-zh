# C |宏&预处理器|第 14 题

> 原文:[https://www . geesforgeks . org/c-宏-预处理器-问题-3/](https://www.geeksforgeeks.org/c-macro-preprocessor-question-3/)

以下程序的输出是什么？

```cpp
#include <stdio.h>
#define macro(n, a, i, m) m##a##i##n
#define MAIN macro(n, a, i, m)

int MAIN()
{
    printf("GeeksQuiz");
    return 0;
}
```

**(A)** 编译器错误
**(B)**geek squiz
**(C)**MAIN
**(D)**MAIN

**答案:****(B)**

**解释:**程序有一个预处理器，将“MAIN”替换为“macro(n，A，I，m)”。“macro(n，a，I，m)”行再次被 main 替换。需要注意的关键是[令牌粘贴操作符##](http://msdn.microsoft.com/en-us/library/09dwwt6y(v=vs.80).aspx) ，将参数串联成宏。

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/macro-preprocessor-gq/)