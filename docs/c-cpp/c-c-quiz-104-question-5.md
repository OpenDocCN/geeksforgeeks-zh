# C 小测验–104 |问题 5

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-104-question-5/](https://www.geeksforgeeks.org/c-c-quiz-104-question-5/)

对于**开关**控制表达式，以下哪种说法是正确的？

**(A)** 在“开关”控制表达式中只能使用 int。
**(B)**int 和 char 都可以用在“switch”控制表达式中。
**(C)** 所有类型即 int、char 和 float 都可以用在“switch”控制表达式中。
**(D)** “开关”控制表达式也可以为空。

**回答:****(B)**

**说明:**按照 C 标准，“*switch 语句的控制表达式应为整数类型。*“因为在开关控制表达式中，char 被提示为整数，所以它是允许的，但是 float 不被提升。这就是为什么 B 是正确的说法。

[本题小考](https://www.geeksforgeeks.org/c-quiz-104-gq/)