# C++ |虚函数|问题 7

> 原文:[https://www . geesforgeks . org/c-virtual-functions-question-7/](https://www.geeksforgeeks.org/c-virtual-functions-question-7/)

```cpp
#include<iostream>
using namespace std;

class Base
{
public:
    virtual void show() = 0;
};

class Derived: public Base
{
public:
    void show() { cout<<"In Derived \n"; }
};

int main(void)
{
    Derived d;
    Base &br = d;
    br.show();
    return 0;
}
```

**(A)** 编译器在“Base & br = d”行出错
**(B)** 空输出
**(C)** 在衍生

**回答:****(C)**

**说明:**请参考[c++ 中的纯虚函数和抽象类](https://www.geeksforgeeks.org/pure-virtual-functions-and-abstract-classes/)

[本题的小测验](https://www.geeksforgeeks.org/c-plus-plus-gq/virtual-functions-gq/)