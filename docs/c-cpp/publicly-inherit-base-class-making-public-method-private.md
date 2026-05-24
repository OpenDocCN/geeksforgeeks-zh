# 公开继承一个基类，但是将一些公开的方法设为私有

> 原文:[https://www . geesforgeks . org/public-inherit-base-class-making-public-method-private/](https://www.geeksforgeeks.org/publicly-inherit-base-class-making-public-method-private/)

在某些情况下，我们希望在派生类中将一些公共基类函数设为私有。假设基类和子类都有 getter 和 setter 方法

```cpp
// CPP program to demonstrate that all base
// class public functions become available
// in derived class if we use public inheritance.
#include <iostream>
using namespace std;

class Base {
    int i;

public:
    Base() {}
    void setBaseProperties(int i)
    {
        this->i = i;
    }
    void showBaseProperties()
    {
        std::cout << endl
                  << "i = " << i;
    }
    virtual ~Base() {}
};

class Child : public Base {
    int j;
    int k;

public:
    void setChildProperties(int i, int j, int k)
    {
        setBaseProperties(i);
        this->j = j;
        this->k = k;
    }
    void showChildProperties()
    {
        showBaseProperties();
        cout << " j = " << j << " k = " << k;
    }
};

int main()
{
    Child c;
    c.setChildProperties(1, 2, 3);

    // this exposed function is undesirable
    c.setBaseProperties(4); 

    c.showChildProperties();
    return 0;
}
```

**Output:**

```cpp
i = 4 j = 2 k = 3

```

这里如果我们需要用子类对象“c”来限制函数“setBaseProperties”和“showBaseProperties”的调用。这可以在不覆盖如下功能的情况下实现:

我们使用“使用”语法在派生类范围内重新声明基类函数。我们在派生类的私有部分中完成。

```cpp
// CPP program to demonstrate that some of
// base class public functions cane be restricted
// in derived class if we re-declare them with 
// "using" in private section of derived class
#include <iostream>
using namespace std;

class Base {
    int i;

public:
    Base() {}
    void setBaseProperties(int i)
    {
        this->i = i;
    }
    void showBaseProperties()
    {
        std::cout << endl
                  << "i = " << i;
    }
    virtual ~Base() {}
};

class Child : public Base {
    int j;
    int k;

    // Redeclaring scope of base class
    // functions in private section of
    // derived class.
    using Base::showBaseProperties;
    using Base::setBaseProperties;

public:
    void setChildProperties(int i, int j, int k)
    {
        setBaseProperties(i);
        this->j = j;
        this->k = k;
    }
    void showChildProperties()
    {
        showBaseProperties();
        cout << " j = " << j << " k = " << k;
    }
};

int main()
{
    Child c;
    c.setChildProperties(1, 2, 3);

    // if we uncomment this part of code, it causes 
    // compilation error as the function is private 
    // now
    // c.setBaseProperties(4); 

    c.showChildProperties();
    return 0;
}
```

**Output:**

```cpp
i = 1 j = 2 k = 3

```