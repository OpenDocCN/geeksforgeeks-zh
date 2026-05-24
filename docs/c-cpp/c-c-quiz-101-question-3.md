# C 小测验–101 |问题 3

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-101-question-3/](https://www.geeksforgeeks.org/c-c-quiz-101-question-3/)

```cpp
#include "stdlib.h"
int main()
{
 int *pInt;
 int **ppInt1;
 int **ppInt2;

 pInt = (int*)malloc(sizeof(int));
 ppInt1 = (int**)malloc(10*sizeof(int*));
 ppInt2 = (int**)malloc(10*sizeof(int*));

 free(pInt);
 free(ppInt1);
 free(*ppInt2);
 return 0;
}
```

选择 C 程序上面正确的语句。
**(A)** malloc()对于 ppInt1 和 ppInt2 是不正确的。这会导致编译时错误。
**(B)** 自由(*ppInt2)不正确。这会导致编译时错误。
**(C)** 自由(*ppInt2)不正确。它会产生运行时错误。
**(D)**malloc()和 free()都没有问题，即没有编译/运行时错误。

**回答:****(D)**

**说明:** ppInt2 是指针对指针对 Int。*ppInt2 是指向 Int 的指针。只要 free()的参数是指针，就没有问题。这就是为什么 B)和 C)都不正确的原因。根据其数据类型，ppInt1 和 ppInt2 的分配都很好。所以 A)也是不正确的。正确的说法是 D)。

[本题小考](https://www.geeksforgeeks.org/c-quiz-101-gq/)