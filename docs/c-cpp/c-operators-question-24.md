# C |操作员|第 24 题

> 原文:[https://www.geeksforgeeks.org/c-operators-question-24/](https://www.geeksforgeeks.org/c-operators-question-24/)

```cpp
#include <stdio.h>
int main()
{
   int x = 10;
   int y = (x++, x++, x++);
   printf("%d %d\n", x, y);
   return 0;
}
```

**(A)**13 12
**(B)**13 13
**(C)**10 10
**(D)**编译器相关

**答案:****(A)**

**解释:**逗号运算符定义了一个[序列点](https://www.geeksforgeeks.org/sequence-points-in-c-set-1/)，所以选项(D)不是
所有表达式从左到右执行，最右边表达式的值由逗号运算符返回。

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/operators-gq/)