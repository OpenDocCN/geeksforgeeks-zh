# C |存储类和类型限定符|问题 19

> 原文:[https://www . geesforgeks . org/c-storage-class-and-type-qualifier-question-16/](https://www.geeksforgeeks.org/c-storage-classes-and-type-qualifiers-question-16/)

```cpp
#include <stdio.h>
int main()
{
  extern int i;
  printf("%d ", i);
  {
       int i = 10;
       printf("%d ", i);
  }
}
```

**(A)** 0 10
**(B)** 编译器错误
**(C)**0 0
**(D)**10 10

**答案:****(B)**

**解释:**参见 [extern 关键字](https://www.geeksforgeeks.org/understanding-extern-keyword-in-c/)

[本题小测验](https://www.geeksforgeeks.org/c-language-2-gq/storage-classes-gq/)