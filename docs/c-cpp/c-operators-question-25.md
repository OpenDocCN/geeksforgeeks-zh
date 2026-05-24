# C |操作员|第 26 题

> 原文:[https://www.geeksforgeeks.org/c-operators-question-25/](https://www.geeksforgeeks.org/c-operators-question-25/)

```cpp
#include <stdio.h>
int main()
{
   int y = 0;
   int x = (~y == 1);
   printf("%d", x);
   return 0;
}
```

**(A)**0
**(B)**1
**(C)**A bog 负数
**(D)** 编译器错误

**答案:****(A)**

**解释:**这里要注意的是~是按位非运算符。所以在二进制表示中~0 的值是全 1，这意味着~0 的十进制值不是 1。因此，比较运算符的结果变为 0。

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/operators-gq/)