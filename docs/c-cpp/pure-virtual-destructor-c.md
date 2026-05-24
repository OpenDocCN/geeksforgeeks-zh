# c++ 中的纯虚拟析构函数

> 原文:[https://www.geeksforgeeks.org/pure-virtual-destructor-c/](https://www.geeksforgeeks.org/pure-virtual-destructor-c/)

**析构函数在 C++ 中可以是纯虚函数吗？**
是的，有可能有纯虚析构函数。纯虚拟析构函数在标准 C++ 中是合法的，需要记住的最重要的一点是，如果一个类包含纯虚拟析构函数，它必须为纯虚拟析构函数提供一个函数体。你可能想知道为什么一个纯虚函数需要一个函数体。原因是析构函数(不像其他函数)实际上没有被“覆盖”，而是总是以类派生的相反顺序被调用。这意味着将首先调用派生类的析构函数，然后调用基类析构函数。如果没有提供纯虚析构函数的定义，那么在对象销毁时会调用什么函数体？因此，编译器和链接器强制纯虚拟析构函数存在函数体。
考虑以下程序:

```cpp
#include <iostream>
class Base
{
public:
    virtual ~Base()=0; // Pure virtual destructor
};

class Derived : public Base
{
public:
    ~Derived()
    {
        std::cout << "~Derived() is executed";
    }
};

int main()
{
    Base *b=new Derived();
    delete b;
    return 0;
}
```

链接器将在上述程序中产生以下错误。

```cpp
test.cpp:(.text$_ZN7DerivedD1Ev[__ZN7DerivedD1Ev]+0x4c): 
undefined reference to `Base::~Base()' 
```

现在，如果提供了纯虚拟析构函数的定义，那么程序编译运行良好。

```cpp
#include <iostream>
class Base
{
public:
    virtual ~Base()=0; // Pure virtual destructor
};
Base::~Base()
{
    std::cout << "Pure virtual destructor is called";
}

class Derived : public Base
{
public:
    ~Derived()
    {
        std::cout << "~Derived() is executed\n";
    }
};

int main()
{
    Base *b = new Derived();
    delete b;
    return 0;
}
```

输出:

```cpp
~Derived() is executed
Pure virtual destructor is called
```

需要注意的是，当一个类包含一个纯虚拟析构函数时，它就变成了抽象类。例如，试着编译下面的程序。

```cpp
#include <iostream>
class Test
{
public:
    virtual ~Test()=0; // Test now becomes abstract class
};
Test::~Test() { }

int main()
{
    Test p;
    Test* t1 = new Test;
    return 0;
}
```

上述程序编译失败，并显示以下错误消息。
【错误】无法将变量“p”声明为抽象类型“Test”
【注意】因为以下虚函数在“Test”中是纯的:
【注意】虚拟测试::~Test()
【错误】无法分配抽象类型“Test”
【注意】因为类型“Test”具有纯虚函数

**相关文章:**
[c++ 中的构造函数](https://www.geeksforgeeks.org/constructors-c/)
[c++ 中的析构函数](https://www.geeksforgeeks.org/destructors-c/)
[虚拟析构函数](https://www.geeksforgeeks.org/virtual-destructor/)

来源:
[http://www.bogotobogo.com/cplusplus/virtualfunctions.php](http://www.bogotobogo.com/cplusplus/virtualfunctions.php)T3[http://www . open-STD . org/JT C1/sc22/wg21/docs/papers/2005/n 1905 . pdf](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2005/n1905.pdf)

本文由**遇见普拉瓦西**供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。