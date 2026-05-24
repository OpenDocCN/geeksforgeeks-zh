# C |操作员|第 21 题

> 原文:[https://www.geeksforgeeks.org/c-operators-question-21/](https://www.geeksforgeeks.org/c-operators-question-21/)

假设一个整数的大小是 4 字节，预测下面程序的输出。

```cpp
#include <stdio.h>
int main()
{
    int i = 12;
    int j = sizeof(i++);
    printf("%d  %d", i, j);
    return 0;
}
```

**(A)**12 4
**(B)**13 4
**(C)**编译器错误
**(D)**0 4

**答案:****(A)**

**解释:**sizeof 内部编写的表达式未求值，所以 i++ 不执行。

[本题小考](https://www.geeksforgeeks.org/java-gq/operators-gq/)