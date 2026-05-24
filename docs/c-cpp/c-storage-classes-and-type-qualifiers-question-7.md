# C |存储类和类型限定符|问题 7

> 原文:[https://www . geesforgeks . org/c-storage-class-and-type-qualifier-question-7/](https://www.geeksforgeeks.org/c-storage-classes-and-type-qualifiers-question-7/)

输出？

```cpp
#include<stdio.h>
int main()
{
   typedef int i;
   i a = 0;
   printf("%d", a);
   return 0;
}
```

**(A)** 编译器错误
**(B)** 运行时错误
**(C)**0
**(D)**1

**回答:****(C)**

**说明:**程序没有问题。它只是创建一个用户定义的类型 I，并创建一个类型 I 的变量 a。