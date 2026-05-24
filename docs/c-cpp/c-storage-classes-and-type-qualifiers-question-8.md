# C |存储类和类型限定符|问题 8

> 原文:[https://www . geesforgeks . org/c-storage-class-and-type-qualifier-question-8/](https://www.geeksforgeeks.org/c-storage-classes-and-type-qualifiers-question-8/)

```cpp
#include<stdio.h>
int main()
{
  typedef int *i;
  int j = 10;
  i *a = &j;
  printf("%d", **a);
  return 0;
}
```

**(A)** 编译器错误
**(B)** 垃圾值
**(C)**10
**(D)**0

**答案:****(A)**

**解释:**编译器错误- >初始化时指针类型不兼容。
type def int * I 行将 I 作为 int *类型。所以，a 的声明意味着 a 是指向指针的指针。不同编译器上的错误消息可能不同。