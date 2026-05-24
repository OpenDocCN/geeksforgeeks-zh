# C |存储类和类型限定符|问题 17

> 原文:[https://www . geesforgeks . org/c-storage-class-and-type-qualifier-question-17/](https://www.geeksforgeeks.org/c-storage-classes-and-type-qualifiers-question-17/)

输出？

```cpp
#include <stdio.h>

int main(void)
{
    int i = 10;
    const int *ptr = &i;
    *ptr = 100;
    printf("i = %d\n", i);
    return 0;
}
```

**(A)**I = 100
**(B)**I = 10
**(C)**编译器错误
**(D)** 运行时错误

**回答:****(C)**

**解释:**注意 ptr 是指向常量的指针。因此，不能使用指针 ptr 更改所指向的值。详见 C 中[常量限定符。](https://www.geeksforgeeks.org/const-qualifier-in-c/) [本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)