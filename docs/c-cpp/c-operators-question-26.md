# C |操作员|第 27 题

> 原文:[https://www.geeksforgeeks.org/c-operators-question-26/](https://www.geeksforgeeks.org/c-operators-question-26/)

```cpp
#include <stdio.h>
int main()
{
   int a = 0;
   int b;
   a = (a == (a == 1));
   printf("%d", a);
   return 0;
}
```

**(A)**0
**(B)**1
**(C)**大负数
**(D)**-1

**答案:****(B)**

**解释:**我们需要算出的值为“(A = =(A = = 1))

所以在外括号中，false 与 a 比较。由于 a 为 0，外括号的结果变为 true。

需要注意的重要一点是，在 C 语言中，当一个布尔值被比较或赋给一个整数值时，false 被认为是 0，true 被认为是 1。

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/operators-gq/)