# C 小测验–112 |问题 1

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-112-question-1/](https://www.geeksforgeeks.org/c-c-quiz-112-question-1/)

选择以下计划的最佳陈述:

```cpp
#include "stdio.h"

int main()
{
 struct {int a[2];} arr[] = {{1},{2}};

 printf("%d %d %d %d",arr[0].a[0],arr[0].a[1],arr[1].a[0],arr[1].a[1]);

 return 0;
}
```

**(A)** 编译错误，因为 arr 使用结构类型定义不正确。首先应该使用标记定义结构类型，然后应该使用标记定义 arr。
**(B)** 编译错误，因为除了 arr 的定义，另一个问题是结构数组的初始化，即 arr[]。
**(C)** 编译错误，因为结构数组初始化，即 arr[]。
**(D)** 无编译错误，它将打印 1 2 0 0
**(E)** 无编译错误，它将打印 1 0 2 0

**答案:****(E)**

**解释:**这里，结构类型定义和使用该结构类型的 arr 的定义已经在同一行中完成。按照 C 标准，这是可以的。甚至初始化也是正确的。需要注意的是 arr[]的数组大小是 2，即这个结构类型的数组的 2 个元素。这是由上面的初始化方式决定的。这里，arr[0]。[0]是 1，arr 是[1]。[0]将是 2。数组的剩余元素将是零。正确答案是 e .本题

[小测验](https://www.geeksforgeeks.org/c-quiz-112-gq/)