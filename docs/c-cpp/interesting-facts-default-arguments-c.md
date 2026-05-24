# 关于 C++ 中默认参数的一些有趣事实

> 原文:[https://www . geesforgeks . org/interest-facts-default-arguments-c/](https://www.geeksforgeeks.org/interesting-facts-default-arguments-c/)

预测以下 C++ 程序的输出。

**1)**T0】

上面的程序乍一看是正确的，但编译时会失败。如果函数使用[默认参数](http://geeksquiz.com/default-arguments-c/)，那么默认参数不能写入两个函数声明&定义中。它应该只在声明中，而不是在定义中。

下面的程序现在是正确的。

```cpp
#include <iostream>
void init(int a=1, int b=2, int c=3);
int main()
{
    init(); // It is fine
    return 0;
}
void init(int a,int b,int c)
{
    std::cout << a << ' ' << b << ' ' << c;
}
```

**2)**T0】

如果你仔细观察函数原型，那么它看起来像一个错误，但实际上不是。默认参数中可以省略变量名。

本文由 **Pravasi Meet** 供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。