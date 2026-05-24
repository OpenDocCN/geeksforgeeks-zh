# C++ |继承|第 10 题

> 原文:[https://www.geeksforgeeks.org/c-inheritance-question-10/](https://www.geeksforgeeks.org/c-inheritance-question-10/)

以下程序的输出？

```cpp
#include <iostream>
#include<string>
using namespace std;

class Base
{
public:
    virtual string print() const
    {
        return "This is Base class";
    }
};

class Derived : public Base
{
public:
    virtual string print() const
    {
        return "This is Derived class";
    }
};

void describe(Base p)
{
    cout << p.print() << endl;
}

int main()
{
    Base b;
    Derived d;
    describe(b);
    describe(d);
    return 0;
}
```

**(甲)**

```cpp
This is Derived class
This is Base class
```

**(B)**

```cpp
This is Base class
This is Derived class
```

**(C)**

```cpp
This is Base class
This is Base class
```

**(D)** 编译器错误

**答案:** **(C)**

**解释:**注意:description(D)中传递了一个派生类的对象，但是调用了 Base 的 print。描述函数接受基本类型的参数。

这是一个典型的对象切片的例子，当我们把一个派生类的对象分配给一个基类的对象时，派生类对象被切掉，从基类继承的所有数据成员都被复制。对象切片应该是双向的，因为可能会有类似上面的惊人结果。顺便提一下，对象切片在 Java 中是不可能的。在 Java 中，每个非基元变量实际上都是一个引用。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)