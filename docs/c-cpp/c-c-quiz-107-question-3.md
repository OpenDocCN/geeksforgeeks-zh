# C 小测验–107 |问题 3

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-107-question-3/](https://www.geeksforgeeks.org/c-c-quiz-107-question-3/)

在 C 程序片段中，以下内容用于定义整数变量？

```cpp
signed s;
unsigned u;
long l;
long long ll;
```

为这些选择最好的陈述。
**(A)** 以上所有变量定义都不正确，因为缺少基本数据类型 int。
**(B)** 所有上述变量定义都是正确的，因为所有这些变量都隐含地假设了 int。
**(C)** 只有“长 l；”和“长长的 ll”是变量的有效定义。
**(D)** 仅“无符号 u；”是变量的有效定义。

**回答:****(B)**

**解释:**请注意*有符号的*、*无符号的*和*长的*这三个都是 Type 说明符。而 *int* 在这三者中都是隐含假设的。
按照 C 标准，“int、signed 或 signed int”是等价的。类似地，“无符号或无符号整数”也是等价的。此外，“long、signed long、long int 或 signed long int”都是等价的。和“long long，signed long，long long int，或 signed long long int”是等价的。

[本题小考](https://www.geeksforgeeks.org/c-quiz-107-gq/)