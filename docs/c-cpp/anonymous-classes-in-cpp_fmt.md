# C++ 中的匿名类

> 原文：[https://www.geeksforgeeks.org/anonymous-classes-in-cpp/](https://www.geeksforgeeks.org/anonymous-classes-in-cpp/)

## 匿名类简介

匿名类是一个没有名字的类。C++ 支持这个特性。

*   这些类不能有构造函数，但可以有析构函数。
*   这些类既不能作为函数的参数传递，也不能用作函数的返回值。

## 举例说明匿名类

### 1. 创建匿名类的单个对象

在第一个示例中，匿名类被创建，对象名为 `obj1`。`obj1` 的作用域贯穿整个程序。因此，我们可以在 `main` 函数中访问它。在 `main` 中，使用 `obj1` 调用匿名类的成员函数。

```cpp
// CPP program to illustrate 
// concept of Anonymous Class
#include <iostream>
using namespace std;

// Anonymous Class : Class is not having any name
class
{
    // data member
    int i; 
public:
    void setData(int i)
    {
        // this pointer is used to differentiate
        // between data member and formal argument.
        this->i = i;
    }
    void print()
    {
        cout << "Value for i : " << this->i << endl;
    }

} obj1;     // object for anonymous class

// Driver function
int main()
{
    obj1.setData(10);
    obj1.print();
    return 0;
}
```

输出：

```
Value for i : 10
```

### 2. 创建匿名类的两个对象

在第二个示例中，我们为匿名类创建了两个对象 `obj1` 和 `obj2`，并调用了类的成员函数。`obj1` 和 `obj2` 的作用域贯穿整个程序。同样地，我们可以为匿名类创建多个对象。

```cpp
// CPP program to illustrate 
// concept of Anonymous Class
#include <iostream>
using namespace std;

// Anonymous Class : Class is not having any name
class
{
    // data member
    int i; 
public:
    void setData(int i)
    {
        // this pointer is used to differentiate
        // between data member and formal argument.
        this->i = i;
    }
    void print()
    {
        cout << "Value for i : " << this->i << endl;
    }

} obj1, obj2;    // multiple objects for anonymous class

// Driver function
int main()
{
    obj1.setData(10);
    obj1.print();

    obj2.setData(20);
    obj2.print();
    return 0;
}
```

输出：

```
Value for i : 10
Value for i : 20
```

### 3. 限制匿名类的作用域

为了限制匿名类对象的作用域，我们可以借助 `typedef`。在第三个示例中，通过使用 `typedef`，我们可以为类赋予一个方便的名字，并使用该名字创建多个对象 `obj1` 和 `obj2`。在这里，我们可以控制 `obj1` 和 `obj2` 对象的作用域，它们位于 `main` 函数内部。

```cpp
// CPP program to illustrate 
// concept of Anonymous Class
// by scope restriction
#include<iostream>
using namespace std;

// Anonymous Class : Class is not having any name
typedef class
{
    // data member
    int i; 
public:
    void setData(int i)
    {
        // this pointer is used to differentiate 
        // between data member and formal argument.
        this->i = i;
    }
    void print()
    {
        cout << "Value for i :" << this->i << endl;
    }

} myClass;      // using typedef give a proper name

// Driver function
int main()
{
    // multiple objects
    myClass obj1, obj2; 
    obj1.setData(10);
    obj1.print();

    obj2.setData(20);
    obj2.print();
    return 0;
}
```

输出：

```
Value for i : 10
Value for i : 20
```