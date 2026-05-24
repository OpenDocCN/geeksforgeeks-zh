# C |指针基础|第 17 题

> 原文:[https://www.geeksforgeeks.org/c-pointers-question-11-2/](https://www.geeksforgeeks.org/c-pointers-question-11-2/)

```cpp
#include<stdio.h>
void fun(int arr[])
{
  int i;
  int arr_size = sizeof(arr)/sizeof(arr[0]);
  for (i = 0; i < arr_size; i++)
      printf("%d ", arr[i]);
}

int main()
{
  int i;
  int arr[4] = {10, 20 ,30, 40};
  fun(arr);
  return 0;
} 
```

**(A)**10 20 30 40
**(B)**机器相关
**(C)**10 20
**(D)**北移

**回答:****(B)**

**说明:**在 C 语言中，数组参数始终被视为指针。所以下面两种说法有相同的意思。

```cpp
void fun(int arr[])
void fun(int *arr)

```

[]用于表明函数需要一个数组，但是它不会改变任何东西。人们使用它只是为了可读性，这样读者就能清楚预期的参数类型。底线是，sizeof 永远不应该用于数组参数，数组大小(或长度)的单独参数应该传递给 fun()。所以，**在给定的程序中，arr_size 包含指针大小和整数大小的比值，这个比值=是编译器相关的。**

```cpp
#include <stdio.h>
void fun(int arr[], size_t arr_size)
{
  int i;
  for (i = 0; i < arr_size; i++)
      printf("%d ", arr[i]);
}

int main()
{
  int i;
  int arr[] = {10, 20 ,30, 40};

  // Use of sizeof is fine here
  size_t n = sizeof(arr)/sizeof(arr[0]);
  fun(arr, n);
  return 0;
}
```

产量:
10 20 30 40

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/pointers-gq/)