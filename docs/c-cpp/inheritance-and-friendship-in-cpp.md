# c++ 中的继承和友谊

> 原文:[https://www . geesforgeks . org/继承和友谊 in-cpp/](https://www.geeksforgeeks.org/inheritance-and-friendship-in-cpp/)

C++ 中的**继承:**这是一个 [OOPS](https://www.geeksforgeeks.org/object-oriented-programming-in-cpp/) 的概念。它允许创建从其他类派生的类，以便它们自动包含基类的一些功能和自己的一些功能。(参考[本文](https://www.geeksforgeeks.org/inheritance-in-c/)

**c++ 中的友谊:**通常，类的私有成员和受保护成员不能从声明它们的同一个类之外访问。但是，朋友类可以访问第一个受保护的私有成员。“朋友”类不仅可以访问公共成员，还可以访问私有和受保护的成员。(参考[这篇文章](https://www.geeksforgeeks.org/friend-class-function-cpp/)

**C++ 中继承和友谊的区别:**在 c++ 中，友谊是不继承的。如果基类有友元函数，那么该函数不会成为派生类的友元。

例如，由于基类 *A* 的朋友 试图访问派生类 *B* 的私有数据，下面的程序打印了一个错误。

## C++

```cpp
// CPP Program to demonstrate the relation between
// Inheritance and Friendship
#include <iostream>
using namespace std;

// Parent Class
class A {
protected:
    int x;

public:
    A() { x = 0; }
    friend void show();
};

// Child Class
class B : public A {
private:
    int y;

public:
    B() { y = 0; }
};

void show()
{
    B b;
    cout << "The default value of A::x = " << b.x;

    // Can't access private member declared in class 'B'
    cout << "The default value of B::y = " << b.y;
}

int main()
{
    show();
    getchar();
    return 0;
}
```

**输出**

```cpp
prog.cpp: In function ‘void show()’:
prog.cpp:19:9: error: ‘int B::y’ is private
    int y;
        ^
prog.cpp:31:49: error: within this context
    cout << "The default value of B::y = " << b.y;
                                                ^
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。