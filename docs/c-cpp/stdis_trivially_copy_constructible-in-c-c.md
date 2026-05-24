# STD::is _ trivaly _ copy _ construction in C/c++

> 原文:[https://www . geesforgeks . org/stdis _ trivaly _ copy _ constructionable-in-c-c/](https://www.geeksforgeeks.org/stdis_trivially_copy_constructible-in-c-c/)

**标准::is _ trivaly _ copy _ construction**模板是一种类型，可以从相同类型的值或引用中进行普通构造。这包括标量类型、普通的可复制构造类以及这类类型的数组。这个算法将要测试一个类型是否可以简单地复制和构造。它返回显示相同的布尔值。

**头文件:**

```cpp
#include <type_traits>

```

**模板类:**

```cpp
template <class T> 
struct is_trivially_copy_constructible;

```

如果 **T** 是 _ 平凡 _ 可复制 _ 可构造的，那么它继承自 **true_type** 否则继承自 **false_type** 。

**语法:**

```cpp
std::is_trivially_copy_constructible<int>::value
std::is_trivially_copy_constructible<class T>::value

```

**参数:**该模板接受单个参数 **T(性状类)**来检查 T 是否可以简单复制构建。

**返回值:**该模板返回如下所示的布尔变量:

*   **真:**如果类型是普通的可复制构造的。
*   **False:** 如果类型不是普通的可复制构造的。

下面的程序说明了 C/C++ 中的**STD::is _ trivaly _ copy _ construction**模板:

**程序 1:**

```cpp
// C++ program to illustrate
// is_trivially_copy_constructible
#include <iostream>
#include <type_traits>
using namespace std;

// Struct Class
struct A {
};
struct B {
    B(const B&) {}
};
struct C {
    virtual void fn() {}
};

// Driver Code
int main()
{
    cout << boolalpha;
    cout << "is_trivially_copy_constructible: "
         << endl;
    cout << "int: " << is_trivially_copy_constructible<int>::value
         << endl;
    cout << "A: " << is_trivially_copy_constructible<A>::value
         << endl;
    cout << "B: " << is_trivially_copy_constructible<B>::value
         << endl;
    cout << "C: " << is_trivially_copy_constructible<C>::value
         << endl;
    return 0;
}
```

**Output:**

```cpp
is_trivially_copy_constructible: 
int: true
A: true
B: false
C: false

```

**程序 2:**

```cpp
// C++ program to illustrate
// is_trivially_copy_constructible
#include <iostream>
#include <type_traits>
using namespace std;

// Structure
struct Ex1 {
    string str;
};
struct Ex2 {
    int n;
    Ex2(const Ex2&) = default;
};

// Driver Code
int main()
{
    cout << boolalpha;
    cout << "Ex1 is copy-constructible? ";

    cout << is_copy_constructible<Ex1>::value
         << endl;

    cout << "Ex1 is trivially copy-constructible? ";

    cout << is_trivially_copy_constructible<Ex1>::value
         << endl;

    cout << "Ex2 is trivially copy-constructible? ";

    cout << is_trivially_copy_constructible<Ex2>::value
         << endl;

    cout << "Ex2 is nothrow copy-constructible? ";

    cout << is_nothrow_copy_constructible<Ex2>::value
         << endl;
}
```

**Output:**

```cpp
Ex1 is copy-constructible? true
Ex1 is trivially copy-constructible? false
Ex2 is trivially copy-constructible? true
Ex2 is nothrow copy-constructible? true

```