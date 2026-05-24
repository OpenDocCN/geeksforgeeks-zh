# C |高级指针|问题 2

> 原文:[https://www.geeksforgeeks.org/c-pointers-question-11/](https://www.geeksforgeeks.org/c-pointers-question-11/)

假设一个整数的大小和一个指针是 4 字节。输出？

```cpp
#include <stdio.h>

#define R 10
#define C 20

int main()
{
   int (*p)[R][C];
   printf("%d",  sizeof(*p));
   getchar();
   return 0;
}
```

**(A)**200
**(B)**4
**(C)**800
**(D)**80

**答案:****(C)**

**解释:**输出为 10*20*sizeof(int)，对于整数大小为 4 字节的编译器为“800”。

当指针使用*去引用时，它产生被指向对象的类型。在本例中，它是整数数组的数组。所以，它打印 R*C*sizeof(int)。

[本题竞猜](https://www.geeksforgeeks.org/quiz-corner-gq/)