# C |高级指针|第 10 题

> 原文:[https://www . geesforgeks . org/c-advanced-pointer-question-10/](https://www.geeksforgeeks.org/c-advanced-pointer-question-10/)

以下程序的输出

```cpp
#include <stdio.h>
int fun(int arr[]) {
   arr = arr+1;    
   printf("%d ", arr[0]);
}
int main(void) {
   int arr[2] = {10, 20};
   fun(arr);
   printf("%d", arr[0]);
   return 0;
}
```

**(A)** 编译器错误
**(B)**20 10
**(C)**20 20
**(D)**10 10

**答案:****(B)**

**说明:**在 C 语言中，数组参数被视为指针(见 https://www . geeksforgeks . org)

所以变量 *arr* 在 main()中表示一个数组，但是在 fun()中表示一个指针。

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/advanced-pointer-c-gq/)