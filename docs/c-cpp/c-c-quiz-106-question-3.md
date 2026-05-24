# C 小测验–106 |问题 3

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-106-question-3/](https://www.geeksforgeeks.org/c-c-quiz-106-question-3/)

在 C 程序中，定义了以下变量:

```cpp
float      x = 2.17;
double   y = 2.17;
long double z = 2.17;
```

以下哪一种是通过 printf 打印这些变量的正确方式？
**(A)** printf("%f %lf %Lf "，x，y，z)；
**(B)** printf("%f %f %f "，x，y，z)；
**(C)**printf(" % f % ff % fff "，x，y，z)；
**(D)**printf(" % f % lf % llf "，x，y，z)；

**回答:****(A)**

**说明:**在 C 语言中，float、double 和 long double 都称为实数据类型。对于“float”、“double”和“long double”，正确的格式说明符是上述选项中的%f、%lf 和%Lf。应该注意的是，C 标准也为%g、%e 等实类型指定了其他格式说明符。

[本题小考](https://www.geeksforgeeks.org/c-quiz-106-gq/)