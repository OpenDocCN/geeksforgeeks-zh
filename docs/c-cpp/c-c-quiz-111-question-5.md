# C 小测验–111 |问题 5

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-111-question-5/](https://www.geeksforgeeks.org/c-c-quiz-111-question-5/)

选择以下计划的最佳陈述:

```cpp
#include "stdio.h"

int size = 4;
int arr[size];

int main()
{
 if(arr[0])
  printf("Initialized to ZERO");
 else
  printf("Not initialized to ZERO");

 return 0;
}
```

**(A)** 无编译错误，打印“初始化为零”。
**(B)** 无编译错误，打印“未初始化为零”。
**(C)** 编译错误，因为 arr 的大小是使用任何函数之外的变量定义的。
**(D)** 没有编译错误，它将打印“初始化为零”或“未初始化为零”，这取决于程序特定运行时 arr[0]上的值。

**答案:****(C)**

**说明:**一个大小被指定为变量的数组是不能被任何函数定义出来的。它只能在函数内部定义。所以将 *arr[size]* 放在 main()之外会导致编译错误。答案是 C.

[本题小考](https://www.geeksforgeeks.org/c-quiz-111-gq/)