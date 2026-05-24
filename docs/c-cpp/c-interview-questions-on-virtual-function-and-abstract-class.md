# 关于虚函数和抽象类的 C++ 面试题

> 原文:[https://www . geesforgeks . org/c-面试-虚拟功能和抽象类问题/](https://www.geeksforgeeks.org/c-interview-questions-on-virtual-function-and-abstract-class/)

**1。什么是[纯虚函数](https://www.geeksforgeeks.org/pure-virtual-functions-and-abstract-classes/)？**

**Ans。**c++ 中的纯虚函数(或抽象函数)是我们没有实现的虚函数，我们只声明它。纯虚函数通过在声明中赋值 0 来声明。请参见以下示例。

```cpp
// An abstract class
class Test {
    // Data members of class
public:
    // Pure Virtual Function
    virtual void show() = 0;

    /* Other members */
};
```

**2。什么是抽象类？**
**俺们。**包含至少一个纯虚函数的类称为抽象类。请参见以下示例

```cpp
// An abstract class
class Test {
    // Data members of class
public:
    // Pure Virtual Function
    virtual void show() = 0;

    /* Other members */
};
```

在上面的例子中，Test 是一个抽象类，因为它有一个纯虚函数。

**关于抽象类的一些有趣的事实**
1)我们不能创造一个抽象类的对象。

```cpp
// pure virtual functions make a class abstract
#include <iostream>
using namespace std;

class Test {
    int x;

public:
    virtual void show() = 0;
    int getX() { return x; }
};

int main(void)
{
    Test t;
    return 0;
}
```

**输出:**

```cpp
Compiler Error: cannot declare variable 't' to be of abstract
 type 'Test' because the following virtual functions are pure 
within 'Test': note:     virtual void Test::show() 

```

**2。**我们可以有抽象类类型的指针和引用。
例如，以下程序运行良好。

```cpp
#include <iostream>
using namespace std;

class Base {
public:
    virtual void show() = 0;
};

class Derived : public Base {
public:
    void show() { cout << "In Derived \n"; }
};

int main(void)
{
    Base* bp = new Derived();
    bp->show();
    return 0;
}
```

输出:

```cpp
 In Derived 
```

**3。**如果我们不覆盖派生类中的纯虚函数，那么派生类也就变成了抽象类。
下面的例子说明了同样的情况。

```cpp
#include <iostream>
using namespace std;
class Base {
public:
    virtual void show() = 0;
};

class Derived : public Base {
};

int main(void)
{
    Derived d;
    return 0;
}
```

输出:

```cpp
Compiler Error: cannot declare variable 'd' to be of abstract type 
'Derived'  because the following virtual functions are pure within
'Derived': virtual void Base::show() 

```

**3。**这个程序的输出是什么？

```cpp
#include <iostream>
using namespace std;
class Test {
protected:
    int width, height;

public:
    void set_values(int a, int b)
    {
        width = a;
        height = b;
    }
    virtual int area(void) = 0;
};
class r : public Test {
public:
    int area(void)
    {
        return (width * height);
    }
};
class t : public Test {
public:
    int area(void)
    {
        return (width * height / 2);
    }
};
int main()
{
    r rect;
    t trgl;
    Test* ppoly1 = ▭
    Test* ppoly2 = &trgl;
    ppoly1->set_values(4, 5);
    ppoly2->set_values(4, 5);
    cout << ppoly1->area();
    cout << ppoly2->area();
    return 0;
}
```

输出:

```cpp
2010
```

**说明:**在这个程序中，我们使用抽象类计算矩形和
三角形的面积。

**4。**这个程序的输出是什么？

```cpp
#include <iostream>
using namespace std;
class Base {
public:
    virtual void print() const = 0;
};
class DerivedOne : virtual public Base {
public:
    void print() const
    {
        cout << "1";
    }
};
class DerivedTwo : virtual public Base {
public:
    void print() const
    {
        cout << "2";
    }
};
class Multiple : public DerivedOne, DerivedTwo {
public:
    void print() const
    {
        DerivedTwo::print();
    }
};
int main()
{
    Multiple both;
    DerivedOne one;
    DerivedTwo two;
    Base* array[3];
    array[0] = &both;
    array[1] = &one;
    array[2] = &two;
    for (int i = 0; i < 3; i++)
        array[i]->print();
    return 0;
}
```

输出

```cpp
212
```

**说明:**在这个程序中，我们是根据数组中给出的条件来执行这些的。所以它打印为 212。

**5。**这个程序的输出是什么？

```cpp
#include <iostream>
using namespace std;
class sample {
public:
    virtual void example() = 0;
};
class Ex1 : public sample {
public:
    void example()
    {
        cout << "GeeksForGeeks";
    }
};
class Ex2 : public sample {
public:
    void example()
    {
        cout << " is awesome";
    }
};
int main()
{
    sample* arra[2];
    Ex1 e1;
    Ex2 e2;
    arra[0] = &e1;
    arra[1] = &e2;
    arra[0]->example();
    arra[1]->example();
}
```

输出:

```cpp
 GeeksForGeeks is awesome
```

**说明:**在这个程序中，我们是将来自两个类的两个语句合并，用抽象类打印出来。