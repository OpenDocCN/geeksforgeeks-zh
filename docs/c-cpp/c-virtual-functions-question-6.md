# C++ |虚函数|问题 6

> 原文:[https://www . geesforgeks . org/c-virtual-functions-question-6/](https://www.geeksforgeeks.org/c-virtual-functions-question-6/)

预测后续程序的输出。

```cpp
#include<iostream>
using namespace std;
class Base
{
public:
    virtual void show() = 0;
};

class Derived : public Base { };

int main(void)
{
    Derived q;
    return 0;
}
```

**(A)** 编译器错误:不能有空的派生类
**(B)** 编译器错误:派生类是抽象的
**(C)** 无编译器错误

**答案:****(B)**

**解释:**如果我们不重写派生类中的纯虚函数，那么派生类也就变成了抽象类。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)