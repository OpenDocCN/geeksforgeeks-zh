# C |操作员|第 23 题

> 原文:[https://www.geeksforgeeks.org/c-operators-question-23/](https://www.geeksforgeeks.org/c-operators-question-23/)

预测后续程序的输出？

```cpp
# include <stdio.h>
int main()
{
    int x = 10;
    int y = 20;
    x += y += 10;
    printf (" %d %d", x, y);
    return 0;
}
```

**(A)**40 20
**(B)**40 30
**(C)**30 30
**(D)**30 40

**回答:****(B)**

**说明:**问题中的主语句为“x += y += 10”。由于语句中有两个+=操作符，关联性就出现了。复合赋值运算符的结合性是从右向左的，因此表达式的计算结果为 x += (y += 10)。

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/operators-gq/)