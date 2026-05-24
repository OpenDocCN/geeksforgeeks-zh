# C |循环&控制结构|问题 15

> 原文:[https://www . geesforgeks . org/c-loops-control-structure-question-15/](https://www.geeksforgeeks.org/c-loops-control-structure-question-15/)

在下面的程序中， *X* 代表变量*检查*的数据类型。

```cpp
#include <stdio.h>
int main()
{
    X check;
    switch (check)
    {
        // Some case labels
    }
    return 0;
} 
```

以下哪一项不能代表 *X* ？
**(A)**int
**(B)**char
**(C)**enum
**(D)**float

**答案:****(D)**

**解释:** A switch 表达式可以是 int、char 和 enum。不能在开关内部使用浮点变量/表达式。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)