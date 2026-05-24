# C++ 内部构件|默认构造函数|集合 1

> 原文:[https://www . geesforgeks . org/c-堆内构件-默认-构造函数-set-1/](https://www.geeksforgeeks.org/c-internals-default-constructors-set-1/)

一个没有任何参数或者每个参数都有默认值的构造函数，被称为 ***默认构造函数*** 。默认构造函数的意义是什么？会为每个默认构造函数生成代码吗？会有什么代码被编译器插入到用户实现的默认构造函数的幕后吗？

编译器会隐式*声明*默认构造函数如果不是程序员提供的，会在需要的时候*定义*它。需要编译器定义的默认构造函数来对类内部进行某些初始化。它不会触及数据成员或简单的旧数据类型(像数组、结构等聚合)。但是，编译器会根据情况为默认构造函数生成代码。

考虑从具有默认构造函数的另一个类派生的类，或者包含具有默认构造函数的另一个类对象的类。编译器需要插入代码来调用基类/嵌入对象的默认构造函数。

## C++

```cpp
#include <iostream>
using namespace std;

class Base {
public:
    // compiler "declares" constructor
};

class A {
public:
    // User defined constructor
    A()
    {
        cout << "A Constructor" << endl;
    }

    // uninitialized
    int size;
};

class B : public A {
    // compiler defines default constructor of B, and
    // inserts stub to call A constructor

    // compiler won't initialize any data of A
};

class C : public A {
public:
    C()
    {
        // User defined default constructor of C
        // Compiler inserts stub to call A's constructor
        cout << "C Constructor" << endl;

        // compiler won't initialize any data of A
    }
};

class D {
public:
    D()
    {
        // User defined default constructor of D
        // a - constructor to be called, compiler inserts
        // stub to call A constructor
        cout << "D Constructor" << endl;

        // compiler won't initialize any data of 'a'
    }

private:
    A a;
};

int main()
{
    Base base;

    B b;
    C c;
    D d;

    return 0;
}
```

**Output:** 

```cpp
A Constructor
A Constructor
C Constructor
A Constructor
D Constructor
```

在不同的情况下，编译器需要插入代码，以确保根据语言要求进行一些必要的初始化。我们将在即将发布的帖子中使用它们。我们的目标是了解 C++ 内部，而不是错误地使用它们。
—由 [**文基**](https://www.geeksforgeeks.org/?page_id=2) 创作。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。