# STD::is _ northrow _ default _ 可在 C++ 中构造，示例

> 原文:[https://www . geesforgeks . org/stdis _ northrow _ default _ constructionable-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_nothrow_default_constructible-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的**STD::is _ northrow _ default _ construction**模板存在于**<**type _ traits**>**头文件中。C++ STL 的**STD::is _ north row _ default _ constructionable**模板用于检查给定类型 **T** 是否为默认可构造类型，这是众所周知的不抛出任何异常。如果 **T** 是默认可构造类型，则返回布尔值 true，否则返回 false。

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template <class T>
struct is_nothrow_default_constructible;

```

**语法:**

```cpp
std::is_nothrow_default_constructible::value

```

**参数:**模板**STD::is _ north row _ default _ construction**接受单个参数 **T(Trait 类)**检查 **T** 是否为默认可构造类型。

**返回值:**该模板返回如下所示的布尔变量:

*   真:如果类型 **T** 是 is _ north row _ default _ construction able .
*   假:如果类型 **T** 不是 is _ north row _ default _ construction able .

下面是用 C/C++ 说明**标准::is _ northrow _ default _ construction 模板**的程序:

**程序 1:**

```cpp
// C++ program to illustrate
// std::is_nothrow_default_constructible
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare structures
struct X {
    X(int, float){};
};

struct Y {
    Y(const Y&) {}
};

struct Z {
    int n;
    Z() = default;
};

// Driver Code
int main()
{

    cout << boolalpha;

    // Check if int is nothrow default
    // constructible or not
    cout << "int: "
         << is_nothrow_default_constructible<int>::value
         << endl;

    // Check if struct X is nothrow default
    // constructible or not
    cout << "struct X: "
         << is_nothrow_default_constructible<X>::value
         << endl;

    // Check if struct Y is nothrow default
    // constructible or not
    cout << "struct Y: "
         << is_nothrow_default_constructible<Y>::value
         << endl;

    // Check if struct Z is nothrow default
    // constructible or not
    cout << "struct Z: "
         << is_nothrow_default_constructible<Z>::value
         << endl;

    // Check if constructor X(int, float) is
    // nothrow default constructible or not
    cout << "constructor X(int, float): "
         << is_nothrow_default_constructible<X(int, float)>::value
         << endl;
    return 0;
}
```

**输出:**

```cpp
int: true
struct X: false
struct Y: false
struct Z: true
constructor X(int, float): false

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/is _ northrow _ default _ constructionable/