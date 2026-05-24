# C++ |虚函数|问题 2

> 原文:[https://www . geesforgeks . org/c-virtual-functions-question-2/](https://www.geeksforgeeks.org/c-virtual-functions-question-2/)

预测以下程序的输出

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
    bp->show();

    Base &br = *bp;
    br.show();

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

**回答:** **(C)**

**说明:**由于 show()在基类中是虚的，所以是根据被引用或指向的对象的类型来调用的，而不是指针或引用的类型。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)