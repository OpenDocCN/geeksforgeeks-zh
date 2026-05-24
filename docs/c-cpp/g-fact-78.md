# 逗号运算符在 C 和 C++ 中作为 l 值的结果

> 原文:[https://www.geeksforgeeks.org/g-fact-78/](https://www.geeksforgeeks.org/g-fact-78/)

使用逗号运算符的结果作为 l 值在 C 中是无效的。但是在 C++ 中，如果逗号运算符的右操作数是 l 值，则逗号运算符的结果可以用作 l 值。

例如，如果我们将下面的程序编译为 C++ 程序，那么它可以工作并打印 b = 30。如果我们编译与 C 程序相同的程序，那么它会在编译时给出警告/错误(Dev C++ 中的警告和代码块中的错误)。

```cpp
#include<stdio.h>

int main()
{
  int a = 10, b = 20;
  (a, b) = 30; // Since b is l-value, this statement is valid in C++, but not in C.
  printf("b = %d", b);
  getchar();
  return 0;
}
```

C++ 输出:
T1】b = 30

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。