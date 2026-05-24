# C |操作员|问题 4

> 原文:[https://www.geeksforgeeks.org/c-operators-question-4/](https://www.geeksforgeeks.org/c-operators-question-4/)

```cpp

#include <stdio.h>

int main()
{
    int i;

    i = 1, 2, 3;
    printf("%d", i);

    return 0;
}

```

**(A)**1
**(B)**3
**(C)**垃圾值
**(D)** 编译时错误

**回答:****(A)**

**解释:**逗号充当运算符。赋值运算符的优先级高于逗号运算符。因此，表达式被认为是(i = 1)，2，3 和 1 被分配给变量 I。这道题的测验