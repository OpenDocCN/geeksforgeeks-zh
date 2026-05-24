# 什么是 C++ 中的转换构造函数？

> 原文:[https://www.geeksforgeeks.org/g-fact-35/](https://www.geeksforgeeks.org/g-fact-35/)

**先决条件:**[c++ 中的类型转换和](https://www.geeksforgeeks.org/type-conversion-in-c)[c++ 中显式关键字的使用](https://www.geeksforgeeks.org/g-fact-93)

在 C++ 中，如果一个类有一个可以用单个参数调用的构造函数，那么这个构造函数就变成了转换构造函数，因为这样的构造函数允许自动转换到被构造的类。

**例**

## C++

```cpp
#include <iostream>

class MyClass {
    int a, b;

public:
    MyClass(int i)
    {
        a = i;
        b = i;
    }
    void display()
    {
        std::cout << " a = " << a << " b = " << b << "\n";
    }
};

int main()
{
    MyClass object(10);
    object.display();

    // Single parameter conversion constructor is invoked.
    object = 20;
    object.display();
    return 0;
}
```

**输出:**

```cpp
a = 10 b = 10
a = 20 b = 20
```

**转换构造函数:**有一些构造函数可以将其参数的类型转换成类的类型。编译器使用这些构造函数来执行隐式类类型转换。这些转换是通过调用与分配给对象的值/对象列表相匹配的相应构造函数进行的。

前面的例子只处理一个参数，将其扩展到几个参数，即扩展初始化列表或支撑初始化列表。也就是说，我们将传递给它的参数放在一对大括号({})中。

**多参数示例:**

## C++

```cpp
#include <iostream>

class MyClass {
    int a, b;

public:
    MyClass(int i, int y)
    {
        a = i;
        b = y;
    }
    void display()
    {
        std::cout << " a = " << a << " b = " << b << "\n";
    }
};

int main()
{
    MyClass object(10, 20);
    object.display();

    // Multiple parameterized conversion constructor is invoked.
    object = { 30, 40 };
    object.display();
    return 0;
}
```

**输出:**

```cpp
a = 10 b = 20
a = 30 b = 40
```

**注:**

1.  扩展初始值设定项列表在 C++ 11 等中可用。
2.  我们可以直接尝试在创建对象时给它分配一个扩展的初始化列表。
3.  构造函数的隐式类类型转换特性不会影响其正常行为。
4.  对构造函数使用显式函数说明符会移除使用该构造函数的隐式转换

**转换构造函数的用法**

**1。函数返回值:**

当函数的返回类型是类时，我们可以返回一个*支撑初始化列表*，而不是返回一个对象，现在由于返回类型是一个类实例，该类的一个对象是用*支撑初始化列表*创建的，假设该类有一个相应的转换构造函数。

**示例:**

> MyClass create_object(int x，int y)
> {
> 返回{x，y }；

该函数 *create_object* 将返回一个 MyClass 对象，该对象的 a 和 b 值与传递给该函数的 x 和 y 值相同。

**2。作为函数的参数:**
当函数的参数类型是一个类时，我们可以将一个*支撑-初始化-列表*作为实际参数传递给函数，而不是将一个对象传递给函数，假设这个类有一个相应的转换构造函数。

**一个例子:**

> void display _ object(MyClass obj)
> {
> obj . display()；
> }
> //该函数在主函数中调用，参数为两个整数的支撑-初始化列表。
> //例如:
> // display_object({10，20 })；

**注意:**这个函数 *display_object* 创建一个名为 obj 的 MyClass 的新类实例，并将调用其成员函数 display()。

演职员表:巴拉思·维涅什·J·K