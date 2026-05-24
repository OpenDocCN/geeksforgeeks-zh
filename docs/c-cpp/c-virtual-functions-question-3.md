# C++ |虚函数|问题 3

> 原文:[https://www . geesforgeks . org/c-virtual-functions-question-3/](https://www.geeksforgeeks.org/c-virtual-functions-question-3/)

以下程序的输出

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
    Base *bp, b;
    Derived d;
    bp = &d;
    bp->show();
    bp = &b;
    bp->show();
    return 0;
}
```

**(甲)**

```cpp
In Base 
In Base 

```

**(B)**

```cpp
In Base 
In Derived

```

**(C)**

```cpp
In Derived
In Derived

```

**(D)**

```cpp
In Derived
In Base 

```

**回答:** **(D)**

**解释:**最初基指针指向一个派生类对象。之后指向基类对象，

[本题小测验](https://www.geeksforgeeks.org/quiz-corner-gq/)