# C |操作员|问题 5

> 原文:[https://www.geeksforgeeks.org/c-operators-question-5/](https://www.geeksforgeeks.org/c-operators-question-5/)

```cpp
#include <stdio.h>
int main()
{
    int i = 3;
    printf("%d", (++ i)++);
    return 0;
}
```

以上程序的输出是什么？
**(A)**3
**(B)**4
**(C)**5
**(D)**编译时错误

**答案:****(D)**

**解释:**在 C 中，前缀和后缀运算符需要 l 值来执行运算并返回 r 值。表达式 **(++ i)++** 在执行时增加变量 I 的值(I 是 l 值)并返回 r 值。当编译器尝试后递增 r 值时，会生成错误(需要 l 值)。