# 虚函数可以用 C++ 内联吗？

> 原文:[https://www.geeksforgeeks.org/inline-virtual-function/](https://www.geeksforgeeks.org/inline-virtual-function/)

[虚函数](https://www.geeksforgeeks.org/virtual-functions-and-runtime-polymorphism-in-c-set-1-introduction/)是使用关键字 Virtual 在基类中声明的成员函数，可以被派生类重写。它们用于实现**运行时多态**或者说**后期绑定**或者**动态绑定。**

[内联函数](https://www.geeksforgeeks.org/inline-functions-cpp/)用于在编译时用内联函数的定义替换函数调用位置。它们用于提高效率。内联函数背后的整个思想是，每当调用内联函数时，内联函数的代码都会在编译时的内联函数调用点被插入或替换。当程序中频繁使用和多次调用小函数时，内联函数非常有用。

**默认情况下，**类内部定义的所有函数都被隐式或自动视为内联函数，虚函数除外。

> **注意:**内联是对编译器及其编译器选择是否内联的请求。

**虚函数可以内联吗？**

无论何时使用基类引用或指针调用虚拟函数，都不能内联，因为调用是在运行时解析的，但是无论何时使用该类的对象(没有引用或指针)调用，都可以内联，因为编译器在编译时知道对象的确切类。

## C++

```cpp
// CPP program to demonstrate that
// virtual functions can be inlined
#include <iostream>
using namespace std;

class Base {
public:
    virtual void who() { cout << "I am Base\n"; }
};
class Derived : public Base {
public:
    void who() { cout << "I am Derived\n"; }
};

int main()
{
    // Part 1
    Base b;
    b.who();

    // Part 2
    Base* ptr = new Derived();
    ptr->who();

    return 0;
}
```

**Output**

```cpp
I am Base
I am Derived
```

**说明:**在**第 1 部分，**通过类的对象调用虚函数 who()。因为它将在编译时被解析，所以它可以被内联。在**第 2 部分**中，虚函数是通过指针调用的，所以不能内联。

本文由**遇见普拉瓦西**供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。