# C |存储类和类型限定符|问题 6

> 原文:[https://www . geesforgeks . org/c-storage-class-and-type-qualifier-question-6/](https://www.geeksforgeeks.org/c-storage-classes-and-type-qualifiers-question-6/)

```cpp
#include<stdio.h>
int main()
{
  typedef static int *i;
  int j;
  i a = &j;
  printf("%d", *a);
  return 0;
}
```

**(A)** 运行时错误
**(B)** 0
**(C)** 垃圾值
**(D)** 编译器错误

**答案:****(D)**

**解释:**编译器错误- >多个存储类为一个。
在 C 中，typedef 被认为是一个[存储不同编译器上的错误消息可能不同。](http://www.itee.uq.edu.au/~comp2303/Leslie_C_ref/C/CONCEPT/storage_class.html)