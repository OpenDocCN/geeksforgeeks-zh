# C |功能|问题 11

> 原文:[https://www.geeksforgeeks.org/c-functions-question-1/](https://www.geeksforgeeks.org/c-functions-question-1/)

以下程序的输出？

```cpp
#include <stdio.h>
int main()
{
    int i = 5;
    printf("%d %d %d", i++, i++, i++);
    return 0;
}
```

**(A)**7 6 5
**(B)**5 6 7
**(C)**7 7 7
**(D)**编译器相关

**答案:****(D)**

**解释:**当参数传递给函数时，每个参数的值在传递给函数之前都会被求值。

参数的求值顺序是什么——从左到右还是从右到左？
如果评估顺序是从左到右，那么输出应该是 5 6 7，如果评估顺序是从右到左，那么输出应该是 7 6 5。不幸的是，C 标准没有定义固定的顺序。编译器可以选择从左到右进行计算。

所以输出依赖于编译器。

[本题竞猜](https://www.geeksforgeeks.org/c-language-2-gq/functions-gq/)