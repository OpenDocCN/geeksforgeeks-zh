# 逗号运算符应谨慎使用

> 原文:[https://www.geeksforgeeks.org/g-fact-41/](https://www.geeksforgeeks.org/g-fact-41/)

在 C 和 C++ 中，逗号是[优先表](http://www.cppreference.com/wiki/operator_precedence)中的最后一个运算符。所以在赋值表达式的右边要小心使用逗号。例如，在下面的程序中，可以预期输出为 b = 10。但是程序打印 b = 20，因为赋值比逗号具有更高的优先级，语句“b = 20，a”变得相当于(b = 20，a)”。

```cpp
#include<stdio.h>
int main()
{
  int a = 10, b;
  b = 20, a;   // b = 20
  printf(" b = %d ", b);
  getchar();
  return 0;
}
```

用逗号括起括号使 b = a(或 10)。

```cpp
#include<stdio.h>
int main()
{
  int a = 10, b;
  b = (20, a); // b = a
  printf(" b = %d ", b);
  getchar();
  return 0;
}
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。