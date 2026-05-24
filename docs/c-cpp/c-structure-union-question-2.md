# C |结构&联合|问题 2

> 原文:[https://www.geeksforgeeks.org/c-structure-union-question-2/](https://www.geeksforgeeks.org/c-structure-union-question-2/)

假设整数大小是 32 位。以下程序的输出是什么？

```cpp
#include<stdio.h>
struct st
{
    int x;
    static int y;
};

int main()
{
    printf("%d", sizeof(struct st));
    return 0;
}
```

**(A)**4
**(B)**8
**(C)**编译器错误
**(D)** 运行时错误

**答案:****(C)**

**解释:**在 C 语言中，结构体和联合类型不能有静态成员。在 C++ 中，结构类型允许有静态成员，但是联合在 C++ 中也不能有静态成员。