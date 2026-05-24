# c++ 中的默认方法，示例

> 原文:[https://www . geesforgeks . org/default-methods-in-c-with-examples/](https://www.geeksforgeeks.org/default-methods-in-c-with-examples/)

如果我们写一个[类](https://www.geeksforgeeks.org/c-classes-and-objects/)里面没有方法，并且这个类没有从另一个类继承，编译器会自动给它添加六个方法。编译器可以自动生成的方法有:

1.  [**【默认构造函数】**](https://www.geeksforgeeks.org/c-internals-default-constructors-set-1/) **:相当于一个空的默认构造函数。默认构造函数是一个可以在没有参数的情况下调用的构造函数。在没有初始化的情况下创建实例时调用它。** 

```cpp
class_name object_name;
```

1.  考虑从具有默认构造函数的另一个类派生的类，或者包含具有默认构造函数的另一个类对象的类。编译器需要插入代码来调用基类/嵌入对象的默认构造函数。

## 卡片打印处理机（Card Print Processor 的缩写）

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