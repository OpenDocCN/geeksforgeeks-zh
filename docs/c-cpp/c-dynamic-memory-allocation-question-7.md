# C |动态内存分配|问题 7

> 原文:[https://www . geesforgeks . org/c-dynamic-memory-allocation-question-7/](https://www.geeksforgeeks.org/c-dynamic-memory-allocation-question-7/)

下面的代码有什么问题？

```cpp
#include<stdio.h>
int main()
{
    int *p = (int *)malloc(sizeof(int));

    p = NULL;

    free(p);
}
```

**(A)** 编译器错误:free 不能应用于 NULL 指针
**(B)** 内存泄漏
**(C)** 悬空指针
**(D)** 当 free()被调用于 NULL 指针时，程序可能会崩溃。

**回答:****(B)**

**说明:** free()可以为 NULL 指针调用，所以 free 函数调用没问题。

问题是内存泄漏，p 被分配了一些没有被释放的内存，但是指针被分配为空。正确的顺序应该如下:

```cpp
    free(p);
    p = NULL;

```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)