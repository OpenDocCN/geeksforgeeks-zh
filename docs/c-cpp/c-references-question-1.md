# C++ |参考文献|问题 1

> 原文:[https://www.geeksforgeeks.org/c-references-question-1/](https://www.geeksforgeeks.org/c-references-question-1/)

如果在调用前 p 的值被初始化为 5，f(p，p)的返回值是多少？注意，第一个参数是通过引用传递的，而第二个参数是通过值传递的。

```cpp
int f(int &x, int c) {
   c  = c - 1;
   if (c == 0) return 1;
   x = x + 1;
   return f(x, c) * x;
} 
```

**(A)**3024
**(B)**6561
**(C)**55440
**(D)**161051

**答案:****(B)**

**解释:**既然 C 是通过值传递的，x 是通过引用传递的，那么所有函数都会有相同的副本

f(5，5) = f(x，4)*x = f(x，3)*x*x = f(x，2)*x*x*x = f(x，1)* x * x * x * x = 1 * x * x * x = x^4

因为 x 在每次函数调用中都递增，所以在 f(x，2)调用后它变成 9。所以表达式 x^4 的值变成了 6561 的 9^4。

```cpp
#include <stdio.h>

int f(int &x, int c)
{
    c  = c - 1;
    if (c == 0) return 1;
    x = x + 1;
    return f(x, c) * x;
}
int main()
{
    int p = 5;
    printf("%d", f(p, p));
}
```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)