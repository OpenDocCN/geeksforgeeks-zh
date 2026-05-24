# C++ |继承|问题 8

> 原文:[https://www.geeksforgeeks.org/c-inheritance-question-8/](https://www.geeksforgeeks.org/c-inheritance-question-8/)

```cpp
#include<iostream>
using namespace std;

class Base
{
public:
    int fun()  { cout << "Base::fun() called"; }
    int fun(int i)  { cout << "Base::fun(int i) called"; }
};

class Derived: public Base
{
public:
    int fun() {  cout << "Derived::fun() called"; }
};

int main()
{
    Derived d;
    d.fun(5);
    return 0;
}
```

**(A)** Base::fun(int i)叫
**(B)** Derived::fun()叫
**(C)** Base::fun()叫
**(D)** 编译器错误

**答案:****(D)**

**解释:**如果一个派生类写自己的方法，那么基类的所有函数都用同一个名字

在上面的问题中，当 fun()在派生类中重写时，同时隐藏了基类的 fun()和 fun(int)。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)