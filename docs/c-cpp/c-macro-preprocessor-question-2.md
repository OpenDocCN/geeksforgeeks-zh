# C |宏&预处理器|问题 2

> 原文:[https://www . geesforgeks . org/c-宏-预处理器-问题-2/](https://www.geeksforgeeks.org/c-macro-preprocessor-question-2/)

```cpp
#include <stdio.h>
#if X == 3
    #define Y 3
#else
    #define Y 5
#endif

int main()
{
    printf("%d", Y);
    return 0;
}
```

以上程序的输出是什么？
**(A)**3
**(B)**5
**(C)**3 或 5 取决于 X 的值
**(D)** 编译时错误

**答案:****(B)**

**解释:**首先看，输出似乎是编译时错误，因为宏 X 还没有定义。在 C 语言中，如果没有定义宏，默认情况下，预处理器会为其分配 0。因此，控制转到条件 else 部分，并打印 5。为了更好的理解，请看下一个问题。