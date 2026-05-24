# c++ 中的静态数据成员

> 原文:[https://www.geeksforgeeks.org/static-data-members-c/](https://www.geeksforgeeks.org/static-data-members-c/)

静态数据成员是使用静态关键字声明的类成员。静态成员具有某些特殊特征。这些是:

*   对于整个类，只创建该成员的一个副本，并由该类的所有对象共享，无论创建了多少对象。
*   它在这个类的任何对象被创建之前被初始化，甚至在 main 启动之前。
*   它只在类中可见，但它的生命周期是整个程序

**语法**

静态数据类型 data _ member _ name

## C++

```cpp
#include <iostream>
using namespace std;

class A
{
public:
    A() { cout << "A's Constructor Called " << endl;  }
};

class B
{
    static A a;
public:
    B() { cout << "B's Constructor Called " << endl; }
};

int main()
{
    B b;
    return 0;
}
```

**输出:**

```cpp
B's Constructor Called
```

上面的程序只调用 B 的构造函数，不调用 A 的构造函数。原因很简单，*静态成员只在类声明中声明，没有定义。必须使用* *范围解析运算符*在类外明确定义它们。
如果我们试图在没有明确定义静态成员“a”的情况下访问它，我们将会得到一个编译错误。例如，以下程序在编译中失败。

## C++

```cpp
#include <iostream>
using namespace std;

class A
{
    int x;
public:
    A() { cout << "A's constructor called " << endl;  }
};

class B
{
    static A a;
public:
    B() { cout << "B's constructor called " << endl; }
    static A getA() { return a; }
};

int main()
{
    B b;
    A a = b.getA();
    return 0;
}
```

**输出:**

```cpp
Compiler Error: undefined reference to `B::a' 
```

如果我们添加了 A 的定义，程序将正常工作，并调用 A 的构造函数。请参见以下程序。

## C++

```cpp
#include <iostream>
using namespace std;

class A
{
    int x;
public:
    A() { cout << "A's constructor called " << endl;  }
};

class B
{
    static A a;
public:
    B() { cout << "B's constructor called " << endl; }
    static A getA() { return a; }
};

A B::a;  // definition of a

int main()
{
    B b1, b2, b3;
    A a = b1.getA();

    return 0;
}
```

**输出:**

```cpp
A's constructor called
B's constructor called
B's constructor called
B's constructor called
```

请注意，上面的程序为 3 个对象(b1、b2 和 b3)调用了 B 的构造函数 3 次，但只调用了 A 的构造函数一次。原因是，*静态成员在所有对象之间共享。这就是为什么它们也被称为类成员或类字段*。此外，*静态成员可以在没有任何对象的情况下访问*，参见下面的程序，其中静态成员“a”在没有任何对象的情况下被访问。

## C++

```cpp
#include <iostream>
using namespace std;

class A
{
    int x;
public:
    A() { cout << "A's constructor called " << endl;  }
};

class B
{
    static A a;
public:
    B() { cout << "B's constructor called " << endl; }
    static A getA() { return a; }
};

A B::a;  // definition of a

int main()
{
    // static member 'a' is accessed without any object of B
    A a = B::getA();

    return 0;
}
```

**输出:**

```cpp
A's constructor called
```

如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息