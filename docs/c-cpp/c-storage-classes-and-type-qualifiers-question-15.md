# C |存储类和类型限定符|问题 19

> 原文:[https://www . geesforgeks . org/c-storage-class-and-type-qualifier-question-15/](https://www.geeksforgeeks.org/c-storage-classes-and-type-qualifiers-question-15/)

输出？

```cpp
#include <stdio.h>
int main()
{
  register int i = 10;
  int *ptr = &i;
  printf("%d", *ptr);
  return 0;
}
```

**(A)** 在所有编译器上打印 10
**(B)**可能生成编译器错误
**(C)** 在所有编译器上打印 0
**(D)**可能生成运行时错误

**答案:****(B)**

**解释:**参见[寄存器关键字](https://www.geeksforgeeks.org/understanding-register-keyword/)
T25 第 1 点