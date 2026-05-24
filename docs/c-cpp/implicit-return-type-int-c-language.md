# C 中的隐式返回类型 int

> 原文:[https://www . geesforgeks . org/implicit-return-type-int-c-language/](https://www.geeksforgeeks.org/implicit-return-type-int-c-language/)

预测后续 C 程序的输出。

```cpp
#include <stdio.h>
fun(int x)
{
    return x*x;
}
int main(void)
{
    printf("%d", fun(10));
    return 0;
}
```

产出:100

需要注意的重要一点是，没有 fun()的返回类型，程序在大多数 C 编译器中仍然编译运行良好。在 C 语言中，如果我们不指定返回类型，编译器会假定隐式返回类型为 int。然而，C99 标准不允许省略返回类型，即使返回类型是 int。这在旧的 C 标准 C89 中是允许的。

在 C++ 中，除了像 Turbo C++ 这样的少数老 C++ 编译器之外，上述程序都是无效的。每个函数都应该在 C++ 中指定返回类型。

本文由 **Pravasi Meet** 供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论