# C | Misc |问题 5

> 原文:[https://www.geeksforgeeks.org/c-misc-question-5/](https://www.geeksforgeeks.org/c-misc-question-5/)

假设一个整数的大小是 4 字节。预测产量？

```cpp
#include <stdio.h>
int fun()
{
    puts(" Hello ");
    return 10;
}

int main()
{
    printf("%d", sizeof(fun()));
    return 0;
}
```

**(A)**4
**(B)**Hello 4
**(C)**4 Hello
**(D)**编译器错误

**答案:****(A)**

**解释:** sizeof()是一个运算符，不是函数。不过，它看起来像一个函数。

运算符的操作数不需要计算。这就是为什么 fun()没有被调用的原因。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)