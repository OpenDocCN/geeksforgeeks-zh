# C |操作员|问题 6

> 原文:[https://www.geeksforgeeks.org/c-operators-question-6/](https://www.geeksforgeeks.org/c-operators-question-6/)

下面程序的输出是什么？

```cpp
#include <stdio.h>
int foo(int* a, int* b)
{
    int sum = *a + *b;
    *b = *a;
    return *a = sum - *b;
}
int main()
{
    int i = 0, j = 1, k = 2, l;
    l = i++ || foo(&j, &k);
    printf("%d %d %d %d", i, j, k, l);
    return 0;
}
```

**(A)**1 2 1 1
**(B)**1 1 2 1
**(C)**1 2 2 1
**(D)**1 2 2

**回答:****(A)**

**解释:**只有当第一个表达式的结果为 FALSE 时，逻辑 OR 中的控件才会转到第二个表达式。调用函数 foo()是因为 **i++** 将 I 的值递增 1 后返回 0(后递增)。foo()函数实际上交换了两个变量的值，并返回第二个参数的值。因此，变量 j 和 k 的值被交换，OR 表达式计算为真。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)