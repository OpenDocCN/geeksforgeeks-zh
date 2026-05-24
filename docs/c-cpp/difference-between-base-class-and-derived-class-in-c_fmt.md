# C++ 中基类和派生类的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-base-class-and-derived-class-in-c/](https://www.geeksforgeeks.org/difference-between-base-class-and-derived-class-in-c/)

[`基类`](https://www.geeksforgeeks.org/inheritance-in-c/)：基类是[面向对象编程语言](https://www.geeksforgeeks.org/object-oriented-programming-in-cpp/)中的一个类，其他类都是从这个类派生出来的。继承基类的类拥有基类的所有成员，还可以有一些附加属性。基类成员和成员函数继承到派生类的对象。基类也称为**父类**或**超类**。

[`派生类`](https://www.geeksforgeeks.org/inheritance-in-c/)：从现有类创建的类。派生类继承基类的所有成员和成员函数。派生类相对于基类可以有更多的功能，并且可以很容易地访问基类。派生类也称为**子类**或**子类**。

**创建派生类的语法：**

```cpp
class BaseClass{
  // members....
  // member function 
}

class DerivedClass : public BaseClass{
  // members....
  // member function 
}
```

**基类和派生类的区别：**

| 序号 | 基类 | 派生类 |
| :--- | :--- | :--- |
| 1。 | 继承属性的类。 | 从基类继承而来的类。 |
| 2。 | 也称为父类或超类。 | 也称为子类。 |
| 3。 | 不能继承派生类的属性和方法。 | 可以继承基类的属性和方法。 |
| 4。 | **语法：** `class base_classname{ … }`。 | **语法：** `class derived_classname : access_mode base_class_name {…}`。 |

下面是说明**基类**和**派生类**的程序：

## 示例程序

```cpp
// C++ program to illustrate
// Base & Derived Class

#include <iostream>
using namespace std;

// Declare Base Class
class Base {
public:
    int a;
};

// Declare Derived Class
class Derived : public Base {
public:
    int b;
};

// Driver Code
int main()
{
    // Initialise a Derived class geeks
    Derived geeks;

    // Assign value to Derived class variable
    geeks.b = 3;

    // Assign value to Base class variable
    // via derived class
    geeks.a = 4;

    cout << "Value from derived class: "
         << geeks.b << endl;

    cout << "Value from base class: "
         << geeks.a << endl;

    return 0;
}
```

**输出：**

```cpp
Value from derived class: 3
Value from base class: 4
```