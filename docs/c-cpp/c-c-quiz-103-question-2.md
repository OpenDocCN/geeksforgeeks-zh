# C 小测验–103 |问题 2

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-103-question-2/](https://www.geeksforgeeks.org/c-c-quiz-103-question-2/)

当我们编译并运行下面的 C 程序片段时会发生什么？

```cpp
#include "stdio.h"
int main()
{
 int a = 10;
 int b = 15;

 printf("=%d",(a+1),(b=a+2));
 printf(" %d=",b);

 return 0;
}
```

**(A)**= 11 15 =
**(B)**= 11 12 =
**(C)**由于第一个 printf()中的(b=a+2)导致编译器错误。
**(D)** 无编译错误，但输出为=11 X=其中 X 取决于编译器实现。

**回答:****(B)**

**说明:**按照 C 标准 C11，printf()的所有参数，不管是否打印，都要进行评估。这就是为什么(b=a+2)也会被求值，b 的值在第一次 printf()之后会是 12。这就是为什么正确答案是 B.

[本题小考](https://www.geeksforgeeks.org/c-quiz-103-gq/)