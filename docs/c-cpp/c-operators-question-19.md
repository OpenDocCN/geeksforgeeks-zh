# C |操作员|第 26 题

> 原文:[https://www.geeksforgeeks.org/c-operators-question-19/](https://www.geeksforgeeks.org/c-operators-question-19/)

下面的语句是做什么的？

```cpp
x  = x | 1 << n;
```

**(A)** 设置 x 为 2<sup>n</sup>
T5【B)设置 x 的第(n+1)位
**(C)** 切换 x 的第(n+1)位
**(D)** 取消 x 的第(n+1)位

**回答:****(B)**

**解释**

如果我们对任意数字 x 的二进制 00001000 进行按位或运算，将从左侧设置其第(n+1)位。

[本题竞猜](https://www.geeksforgeeks.org/c-language-2-gq/operators-gq/)