# C++ |模板|第 9 题

> 原文:[https://www.geeksforgeeks.org/c-templates-question-9/](https://www.geeksforgeeks.org/c-templates-question-9/)

输出？

```cpp
#include <iostream>
using namespace std;

template <class T>
T max (T &a, T &b)
{
    return (a > b)? a : b;
}

template <>
int max <int> (int &a, int &b)
{
    cout << "Called ";
    return (a > b)? a : b;
}

int main ()
{
    int a = 10, b = 20;
    cout << max <int> (a, b);
}
```

**(A)** 20
**(B)** 调用 20
**(C)** 编译器错误

**回答:****(B)**

**说明:**以上程序是模板特殊化的一个例子。有时，我们希望对于特定的数据类型，函数/类模板有不同的行为。为此，我们可以为该特定数据类型创建一个专用版本。

[本题小测验](https://www.geeksforgeeks.org/quiz-corner-gq/)