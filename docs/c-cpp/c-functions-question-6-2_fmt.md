# C |功能|问题 6

> 原文:[https://www.geeksforgeeks.org/c-functions-question-6-2/](https://www.geeksforgeeks.org/c-functions-question-6-2/)

以下程序的输出？

```cpp
#include<stdio.h>

void dynamic(int s, ...)
{
    printf("%d ", s);
}

int main()
{
    dynamic(2, 4, 6, 8);
    dynamic(3, 6, 9);
    return 0;
}
```

**(A)** 2 3
**(B)** 编译错误
**(C)**4 3
**(D)**3 2

**答案:****(A)**

**解释:**在 C 中三个连续的点被称为省略号，它是函数的可变参数数。参数的值是一个一个指定的。现在的问题是如何访问其他参数。详见[本](https://www.geeksforgeeks.org/how-to-count-variable-numbers-of-arguments-in-c/)。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)