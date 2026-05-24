# C 小测验–103 |问题 4

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-103-question-4/](https://www.geeksforgeeks.org/c-c-quiz-103-question-4/)

“stdio.h”中的以下哪些功能可以代替 **printf()** ？

**(A)** fputs()以 FILE 流为标准输出。
**(B)** fprintf()以 FILE 流为 stdout。
**(C)** 以 FILE 流为标准输出的 fwrite()。
**(D)** 以上三者——a、b、c.
**(E)** 在“stdio.h”中，没有 printf()的其他等价函数。

**回答:****(B)**

**解释:**虽然 fputs()和 fwrite()可以接受 FILE stream stdout 并可以输出给定的字符串，但输入的字符串不会导致格式化(即包含格式说明符)的输出。但是 fprintf()可以用于格式化输出。这就是为什么 *fprintf(stdout，" =%d= "，a)；*和 *printf("=%d= "，a)；*两者相当。正确答案是 b .本题

[小测验](https://www.geeksforgeeks.org/c-quiz-103-gq/)