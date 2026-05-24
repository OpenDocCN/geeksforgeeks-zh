# c++ 中的默认参数和虚函数

> 原文:[https://www . geesforgeks . org/default-arguments-and-virtual-function-in-CPP/](https://www.geeksforgeeks.org/default-arguments-and-virtual-function-in-cpp/)

让我们首先理解默认参数和虚函数的含义。

**默认参数:**这些是在函数声明过程中提供的值，这样如果没有参数传递给它们，就可以自动赋值。如果传递了任何值，默认值将被覆盖。

**虚函数:**虚函数是在基类中声明的成员函数，由派生类重新定义(覆盖)。当您使用指向基类的指针或引用来引用派生类对象时，您可以为该对象调用一个虚拟函数并执行该函数的派生类版本。

要查看默认参数与虚函数的组合应用，首先让我们看下面的 C++ 程序，

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate how default arguments and
// virtual function are used together
#include <iostream>
using namespace std;

class Base {
public:
    virtual void fun(int x = 0)
    {
        cout << "Base::fun(), x = " << x << endl;
    }
};

class Derived : public Base {
public:
    virtual void fun(int x)
    {
        cout << "Derived::fun(), x = " << x << endl;
    }
};

// Driver Code
int main()
{
    Derived d1;
    Base* bp = &d1;
    bp->fun();
    return 0;
}
```

**Output**

```cpp
Derived::fun(), x = 0
```

如果我们仔细查看输出，我们会发现派生类的 fun()被调用，并且使用了基类 fun()的默认值。
默认参数不参与函数的签名。因此基类和派生类中 fun()的签名被认为是相同的，因此基类的 fun()被重写。此外，默认值在编译时使用。当编译器发现函数调用中缺少参数时，它会替换给定的默认值。因此，在上面的程序中，x 的值在编译时被替换，在运行时调用派生类的 fun()。

现在预测以下程序的输出，

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate how default arguments and
// virtual function are used together
#include <iostream>
using namespace std;

class Base {
public:
    virtual void fun(int x = 0)
    {
        cout << "Base::fun(), x = " << x << endl;
    }
};

class Derived : public Base {
public:
    virtual void fun(int x = 10) // NOTE THIS CHANGE
    {
        cout << "Derived::fun(), x = " << x << endl;
    }
};

int main()
{
    Derived d1;
    Base* bp = &d1;
    bp->fun();
    return 0;
}
```

**Output**

```cpp
Derived::fun(), x = 0
```

这个程序的输出与前一个程序相同。原因是一样的，默认值在编译时被替换。fun()是在“bp”上调用的，它是一个基本类型的指针。所以编译器替换 0(不是 10)。