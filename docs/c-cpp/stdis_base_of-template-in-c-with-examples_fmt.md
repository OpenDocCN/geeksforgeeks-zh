# std::is_base_of 模板

> 原文: [https://www.geeksforgeeks.org/stdis_base_of-template-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_base_of-template-in-c-with-examples/)

`std::is_base_of` 模板存在于 `<type_traits>` 头文件中。C++ STL 的 `std::is_base_of` 用来检查类 `Base` 是否为 `Derived` 类的基类。它根据上述条件返回布尔值 `true` 或 `false`。

## 头文件

```cpp
#include<type_traits>
```

## 模板类

```cpp
template <class Base, class Derived>
struct is_base_of;
```

## 语法

```cpp
std::is_base_of<A, B>::value
```

## 参数

接受下面两个类作为参数:

*   `Class A` (as the base class): represents the base class.
*   `Class B` (as a derived class): represents a derived class.

## 返回值

该模板返回如下所示的布尔变量:

*   `true`: If the base class (class `A`) is the parent class of the derived class (class `B`).
*   `false`: If the base class (class `A`) is not the parent class of the derived class (class `B`).

下面是用 C/C++ 说明模板 `std::is_base_of` 的程序:

## 程序 1

```cpp
// C++ program to demonstrate the
// std::is_base_of templates
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Base class A
class A {
};

// Derived Class B
class B : A {
};

// Class C
class C {
};

// Driver Code
int main()
{

cout << boolalpha;

// Check if class A is a base class
    // of class B
    cout << "A is base class of B: "
         << is_base_of<A, B>::value
         << endl;

// Check if class B is a base class
    // of class A
    cout << "B is base class of A: "
         << is_base_of<B, A>::value
         << endl;

// Check if class C is a base class
    // of class B
    cout << "C is base class of B: "
         << is_base_of<C, B>::value
         << endl;

// Check if class C is a base class
    // of class C
    cout << "C is base class of C: "
         << is_base_of<C, C>::value
         << endl;

return 0;
}
```

## 输出

```cpp
A is base class of B: true
B is base class of A: false
C is base class of B: false
C is base class of C: true
```

## 参考

[http://www.cplusplus.com/reference/type_traits/is_base_of/](http://www.cplusplus.com/reference/type_traits/is_base_of/)