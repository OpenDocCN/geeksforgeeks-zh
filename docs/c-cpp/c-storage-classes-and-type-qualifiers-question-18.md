# C |存储类和类型限定符|问题 18

> 原文:[https://www . geesforgeks . org/c-storage-class-and-type-qualifier-question-18/](https://www.geeksforgeeks.org/c-storage-classes-and-type-qualifiers-question-18/)

以下程序的输出

```cpp
#include <stdio.h>
int fun(int n)
{
    static int s = 0;
    s = s + n;
    return (s);
}

int main()
{
    int i = 10, x;
    while (i > 0)
    {
        x = fun(i);
        i--;
    }
    printf ("%d ", x);
    return 0;
}
```

**(A)**0
**(B)**100
**(C)**110
**(D)**55

**答案:****(D)**

**说明:**既然 s 是静态的，不同的 I 值就一一加进去。

所以 s 的最终值是

s = i + (i-1) + (i-2) + … 3 + 2 + 1。

s 的值是 i*(i+1)/2。因为 i = 10，s 是 55。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)