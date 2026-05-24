# C |操作员|问题 3

> 原文:[https://www.geeksforgeeks.org/c-operators-question-3/](https://www.geeksforgeeks.org/c-operators-question-3/)

```cpp
#include <stdio.h>

int main()
{
    int i = (1, 2, 3);

    printf("%d", i);

    return 0;
}

```

**(A)**1
**(B)**3
**(C)**垃圾值
**(D)** 编译时错误

**答案:** **(B)**

**说明:**括号运算符的优先级高于赋值运算符。括号内的表达式从左到右计算
，但它总是最后一个被赋值的表达式的结果。