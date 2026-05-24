# C |指针基础|问题 2

> 原文:[https://www.geeksforgeeks.org/c-pointers-question-2/](https://www.geeksforgeeks.org/c-pointers-question-2/)

以下程序的输出？

```cpp
# include <stdio.h>
void fun(int *ptr)
{
    *ptr = 30;
}

int main()
{
  int y = 20;
  fun(&y);
  printf("%d", y);

  return 0;
}
```

**(A)**20
**(B)**30
**(C)**编译器错误
**(D)** 运行时错误

**答案:****(B)**

**解释:**fun()函数期望指针 ptr 指向整数(或整数的地址)。它修改地址 ptr 处的值。取消引用运算符*用于访问地址中的值。在语句“*ptr = 30”中，地址 ptr 处的值被更改为 30。地址运算符&用于获取任何数据类型的变量的地址。在函数调用语句‘fun(&y)’中，y 的地址被传递，因此可以使用 y 的地址对其进行修改。