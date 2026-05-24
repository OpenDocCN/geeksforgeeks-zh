# STD::is _ trivaly _ 可复制 C++ 模板，示例

> 原文:[https://www . geeksforgeeks . org/stdis _ trivaly _ copy able-c-in-template-with-examples/](https://www.geeksforgeeks.org/stdis_trivially_copyable-template-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的**STD::is _ trivaly _ copy**模板存在于**<**type _ traits**>**头文件中。C++ STL 的**STD::is _ trivaly _ copy**模板用于检查 **T** 是否是 trivaly 可复制类型(存储连续的类型)。如果 **T** 是普通可复制类型，则返回布尔值 true，否则返回 false。

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template<class T>
struct is_trivially_copyable;

```

**语法:**

```cpp
std::is_trivially_copyable<T>::value

```

**参数:**模板**STD::is _ trivaly _ copy**接受单个参数 **T(Trait 类)**检查 **T** 是否为 trivaly copy type。

**返回值:**模板**标准::is _ trivaly _ copy**返回如下所示的布尔变量:

*   **真:**如果类型 **T** 是一个平凡可复制的。
*   **假:**如果类型 **T** 不是一个普通的可复制的。

下面是用 C++ 演示**STD::is _ trivaly _ copy**模板的程序:

**程序:**

```cpp
// C++ program to illustrate
// std::is_trivially_copyable
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare structures
struct X {
    int a;
};

struct Y {
    Y(const Y&) {}
};

struct Z {
    virtual void GFG();
};

struct A {
    ~A() = delete;
};

struct B : A {
};

// Driver Code
int main()
{
    cout << boolalpha;

    // Check if X is a trivially
    // copyable or not
    cout << is_trivially_copyable<X>::value
         << endl;

    // Check if Y is a trivially
    // copyable or not
    cout << is_trivially_copyable<Y>::value
         << endl;

    // Check if Z is a trivially
    // copyable or not
    cout << is_trivially_copyable<Z>::value
         << endl;

    // Check if A is a trivially
    // copyable or not
    cout << is_trivially_copyable<A>::value
         << endl;

    // Check if B is a trivially
    // copyable or not
    cout << is_trivially_copyable<B>::value
         << endl;

    return 0;
}
```

**Output:**

```cpp
true
false
false
true
true

```