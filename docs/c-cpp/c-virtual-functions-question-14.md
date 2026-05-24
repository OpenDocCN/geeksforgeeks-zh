# C++ |虚函数|第 14 题

> 原文:[https://www . geesforgeks . org/c-virtual-functions-question-14/](https://www.geeksforgeeks.org/c-virtual-functions-question-14/)

预测后续 C++ 程序的输出

```cpp
#include<iostream>
using namespace std;

class Base
{
public:
    virtual void show() { cout<<" In Base \n"; }
};

class Derived: public Base
{
public:
    void show() { cout<<"In Derived \n"; }
};

int main(void)
{
    Base *bp = new Derived;
    bp->Base::show();  // Note the use of scope resolution here
    return 0;
}
```

**(A)**In Base
**(B)**In Derived
**(C)**编译器错误
**(D)** 运行时错误

**答案:****(A)**

**解释:**一个基类函数即使是虚函数也可以用范围解析运算符访问。

[本题小考](https://www.geeksforgeeks.org/c-plus-plus-gq/virtual-functions-gq/)