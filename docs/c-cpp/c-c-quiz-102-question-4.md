# C 小测验–102 |问题 4

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-102-question-4/](https://www.geeksforgeeks.org/c-c-quiz-102-question-4/)

在浮点(比如 2.1 和 1.1)的模运算(即除法余数)的上下文中，选择最佳语句。

**(A)** 对于浮点，模运算没有定义，所以找不到模。
**(B)** (2.1 % 1.1)是模运算的结果。
**(C)** fmod(2.1，1.1)是模块运行的结果。
**(D)**((int)2.1)%((int)1.1)是模运算的结果。

**回答:****(C)**

**说明:** %只对整数类型起作用而对浮点类型不起作用。将类型转换为整数类型可能会接近预期的结果，但不会产生正确的结果。

基本上， *fmod(x，y* )函数返回 x-ny 的值，对于某个整数 n，这样，如果 y 是非零的，则结果与 x 具有相同的符号，并且大小小于 y 的大小。 *fmod()* 在“math.h”中声明，其原型是“ *double fmod(double x，double y)* ”。对于*浮点*和*长双*也通过 *fmodf()* 和 *fmodl()* 在 math.h 库中实现了模。

[本题小考](https://www.geeksforgeeks.org/c-quiz-102-gq/)