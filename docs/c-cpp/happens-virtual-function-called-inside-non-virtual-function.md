# 在 C++ 中，当在非虚函数内部调用虚函数时会发生什么

> 原文:[https://www . geesforgeks . org/恰巧-虚拟-函数-调用-内部-非虚拟-函数/](https://www.geeksforgeeks.org/happens-virtual-function-called-inside-non-virtual-function/)

预测以下没有任何虚函数的简单 C++ 程序的输出。

```cpp
#include <iostream>
using namespace std;

class Base
{
public:
    void print()
    {
        cout << "Base class print function \n";
    }
    void invoke()
    {
        cout << "Base class invoke function \n";
        this -> print();
    }
};

class Derived: public Base
{
public:
    void print()
    {
        cout << "Derived class print function \n" ;
    }
    void invoke()
    {
        cout << "Derived class invoke function \n";
        this -> print();
    }
};

int main()
{
    Base *b = new Derived;
    b -> invoke();
    return 0;
}
```

**输出:**

```cpp
Base class invoke function
Base class print function
```

由于没有[虚函数](https://www.geeksforgeeks.org/virtual-functions-and-runtime-polymorphism-in-c-set-1-introduction/)，运行时多态行为在上面的代码中不起作用。现在预测下面 C++ 程序的输出。

```cpp
#include <iostream>
using namespace std;

class Base
{
public:
    virtual void print()
    {
        cout << "Base class print function \n";
    }
    void invoke()
    {
        cout << "Base class invoke function \n";
        this -> print();
    }
};

class Derived: public Base
{
public:
    void print()
    {
        cout << "Derived class print function \n" ;
    }
    void invoke()
    {
        cout << "Derived class invoke function \n";
        this -> print(); // called under non - virtual function
    }
};

int main()
{
    Base *b = new Derived;
    b -> invoke();
    return 0;
}
```

**输出:**

```cpp
Base class invoke function
Derived class print function
```

因此，即使在非虚函数中调用虚函数，多态行为也能工作。从以下事实可以猜测输出:要调用的函数是在运行时使用 [vptr 和 vtable](https://www.geeksforgeeks.org/virtual-functions-and-runtime-polymorphism-in-c-set-1-introduction/) 决定的。

本文由 **Sumit Jaiswal** 供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。