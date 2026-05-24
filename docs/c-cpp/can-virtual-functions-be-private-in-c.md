# c++ 中虚函数可以私有吗？

> 原文:[https://www . geesforgeks . org/can-virtual-functions-be-private-in-c/](https://www.geeksforgeeks.org/can-virtual-functions-be-private-in-c/)

在 C++ 中，虚函数可以是私有的，并且可以被派生类重写。例如，下面的程序编译并运行良好。

## C++

```cpp
#include <iostream>

class base
{
public:

    // default base constructor
    base() { std::cout << "base class constructor\n"; }

    // virtual base destructor
    // always use virtual base
    // destructors when you know you
    // will inherit this class
    virtual ~base()
    {
        std::cout << "base class destructor\n";
    }
    // public method in base class
    void show()
    {
        std::cout << "show() called on base class\n";
    }

    // public virtual function in base class,
    // contents of this function are printed when called
    // with base class object when called with base class
    // pointer contents of derived class are printed on
    // screen
    virtual void print()
    {
        std::cout << "print() called on base class\n";
    }
};

class derived : public base {
public:
    // default derived constructor
    derived()
        : base()
    {
        std::cout << "derived class constructor\n";
    }
    // virtual derived destructor
    // always use virtual destructors
    // when inheriting from a
    // base class
    virtual ~derived()
    {
        std::cout << "derived class destructor\n";
    }

private:
    // private virtual function in derived class overwrites
    // base class virtual method contents of this function
    // are printed when called with base class pointer or
    // when called with derived class object
    virtual void print()
    {
        std::cout << "print() called on derived class\n";
    }
};

int main()
{
    std::cout << "printing with base class pointer\n";

    // construct base class pointer with derived class
    // memory
    base* b_ptr = new derived();

    // call base class show()
    b_ptr->show();

    // call virtual print in base class but it is overridden
    // in derived class also note that print() is private
    // member in derived class, still the contents of derived
    // class are printed this code works because base class
    // defines a public interface and drived class overrides
    // it in its implementation
    b_ptr->print();

    delete b_ptr;
}
```

**Output**

```cpp
printing with base class pointer
base class constructor
derived class constructor
show() called on base class
print() called on derived class
derived class destructor
base class destructor

```

上面的程序没什么值得注意的。
b_ ptr 是 Base 类型的指针，指向派生的类对象。调用 ptr- > print() 时，执行派生的 print () 。

这段代码之所以有效，是因为基类定义了一个公共接口，而派生类在其实现中重写了它，即使派生类有一个私有的虚拟函数。
发现有不正确的地方请写评论，或者想分享更多关于上面讨论话题的信息