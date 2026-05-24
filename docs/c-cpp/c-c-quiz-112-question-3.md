# C 小测验–112 |问题 3

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-112-question-3/](https://www.geeksforgeeks.org/c-c-quiz-112-question-3/)

选择以下计划的最佳陈述:

```cpp
#include "stdio.h"

int main()
{
 struct {int a[2], b;} arr[] = {[0].a = {1}, [1].a = {2}, [0].b = 1, [1].b = 2};

 printf("%d %d %d and",arr[0].a[0],arr[0].a[1],arr[0].b);
 printf("%d %d %d\n",arr[1].a[0],arr[1].a[1],arr[1].b);

 return 0;
}
```

**(A)** 编译错误，因为已经指定了结构类型(包含两个字段，即 int 和 int 的数组)以及该结构类型的数组 arr[]的定义。
**(B)** 编译错误，因为数组 arr[]的初始化语法不正确。
**(C)** 没有编译错误，arr[]的两个元素将被定义和初始化。输出将是“1 0 1 和 2 0 2”。
**(D)** 没有编译错误，arr[]的两个元素将被定义和初始化。输出将是“1 X 1 和 2 X 2”，其中 X 是一些垃圾随机数。

**回答:****(C)**

**说明:**在 C 语言中，可以使用指示符提供显式初始化。对于数组，在程序中没有显式初始化的元素被设置为零。这就是为什么正确答案是 C.

[本题小考](https://www.geeksforgeeks.org/c-quiz-112-gq/)