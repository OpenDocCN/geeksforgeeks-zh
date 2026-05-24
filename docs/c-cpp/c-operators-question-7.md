# C |操作员|问题 7

> 原文:[https://www.geeksforgeeks.org/c-operators-question-7/](https://www.geeksforgeeks.org/c-operators-question-7/)

```cpp
#include <stdio.h>
int main()
{
    int i = 5, j = 10, k = 15;
    printf("%d ", sizeof(k /= i + j));
    printf("%d", k);
    return 0;
}
```

假设整数的大小为 4 字节。以上程序的输出是什么？
**(A)**4 1
**(B)**4 15
**(C)**2 1
**(D)**编译时错误

**回答:****(B)**

**说明:**节目的主题就在这里: **sizeof(k /= i + j)】表达式不会在**运算符的**大小中计算。 **sizeof** 运算符返回 sizeof(int)，因为表达式的结果将是一个整数。由于表达式没有求值，所以 **k** 的值不会改变。

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/operators-gq/)**