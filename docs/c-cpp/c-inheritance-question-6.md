# C++ |继承|问题 6

> 原文:[https://www.geeksforgeeks.org/c-inheritance-question-6/](https://www.geeksforgeeks.org/c-inheritance-question-6/)

```cpp
#include<iostream>
using namespace std;

class Base {};

class Derived: public Base {};

int main()
{
    Base *bp = new Derived;
    Derived *dp = new Base;
}
```

**(A)** 无编译器错误
**(B)** 第行编译器错误“Base * bp = new Derived”
**(C)** 第“派生*dp =新基数”行出现编译器错误
**(D)** 运行时错误

**回答:****(C)**

**解释:**一个基类指针/引用可以指向/引用一个派生类对象，但其他方式是不可能的。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)