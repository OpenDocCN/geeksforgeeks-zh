# C 小测验–111 |问题 4

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-111-question-4/](https://www.geeksforgeeks.org/c-c-quiz-111-question-4/)

选择以下计划的最佳陈述:

```cpp
#include "stdio.h"

void fun(int n)
{
   int idx;
   int arr1[n] = {0};
   int arr2[n];

   for (idx=0; idx<n; idx++)
       arr2[idx] = 0;    
}

int main()
{
   fun(4);
   return 0;
}
```

**(A)**arr 1 和 arr2 的定义都不正确，因为变量用于指定数组的大小。这就是为什么编译错误。
**(B)** 除了 arr1 arr2 的定义，arr1 的初始化也不正确。arr1 无法初始化，因为其大小被指定为变量。这就是为什么编译错误。
**(C)**arr 1 初始化不正确。arr1 无法初始化，因为其大小被指定为变量。这就是为什么编译错误。
**(D)** 无编译错误。程序将定义两个数组并将其初始化为零。

**回答:****(C)**

**解释:**对 *arr1* 和 *arr2* 的定义没有问题。在这些数组的定义中，根据 C 标准，使用变量提及数组大小是可以的，但是这些类型的数组不能在定义时初始化。这就是为什么 *arr1* 初始化不正确的原因。但是 *arr2* 的初始化是正确的。正确答案是 C.

[本题小考](https://www.geeksforgeeks.org/c-quiz-111-gq/)