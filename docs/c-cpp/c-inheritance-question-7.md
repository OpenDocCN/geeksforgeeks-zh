# C++ |继承|问题 7

> 原文:[https://www.geeksforgeeks.org/c-inheritance-question-7/](https://www.geeksforgeeks.org/c-inheritance-question-7/)

```cpp
#include<iostream>
using namespace std;

class Base
{
public:
    void show()
    {
        cout<<" In Base ";
    }
};

class Derived: public Base
{
public:
    int x;
    void show()
    {
        cout<<"In Derived ";
    }
    Derived()
    {
        x = 10;
    }
};

int main(void)
{
    Base *bp, b;
    Derived d;
    bp = &d;
    bp->show();
    cout << bp->x;    
    return 0;
}
```

**(A)** 编译器错误行“BP->show()”
**(B)**编译器错误行“cout<x”
**(C)**在 Base 10
**(D)** 在派生类 10

**答案:****(B)**

**解释:**一个基类派生类对象的附加属性被切掉以形成基类对象。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)