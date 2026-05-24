# C |循环&控制结构|问题 7

> 原文:[https://www . geesforgeks . org/c-loops-control-structure-question-7/](https://www.geeksforgeeks.org/c-loops-control-structure-question-7/)

```cpp
#include <stdio.h>
int i;
int main()
{
    if (i);
    else
        printf("Ëlse");
    return 0;
}
```

上述程序的正确之处是什么？
**(一)**若格挡被执行。
**(B)** 否则格挡执行。
**(C)** 不可预测，因为我没有初始化。
**(D)** 错误:放错了别的地方

**回答:****(B)**

**说明:**由于 I 是全局定义的，所以用默认值 0 初始化。如果计算结果为 FALSE，则 Else 块将作为中的表达式执行。请注意，空块相当于一个分号(；).所以陈述**如果(I)；**和 **if (i) {}** 是等价的。