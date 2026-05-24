# STD::is _ 可在 C++ 中构造的模板，示例

> 原文:[https://www . geesforgeks . org/stdis _ constructionable-template-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_constructible-template-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的**STD::is _ construction**模板存在于**<**type _ traits**>**头文件中。C++ STL 的**STD::is _ construction**模板用于检查给定类型 **T** 是否是带参数集的可构造类型。如果 **T** 是可构造类型，则返回布尔值 true，否则返回 false。

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template <class T, class... Args>
struct is_constructible;

```

**语法:**

```cpp
std::is_constructible::value

```

**参数:**

*   **t:** It represents the data type.
*   **args:** means data type list **t** .

**返回值:**该模板返回如下所示的布尔变量:

*   True: if the type **t** is constructable.
*   False: If the type **t** cannot be constructed.

下面是用 C/C++ 说明**标准::is _ 可构造模板**的程序:

**程序:**

```cpp
// C++ program to illustrate
// std::is_constructible example
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare structures
struct A {
};

struct T {
    T(int, int){};
};

// Driver Code
int main()
{
    cout << std::boolalpha;

    // Check if <int> is
    // constructible or not
    cout << "int: "
         << is_constructible<int>::value
         << endl;

    // Check if <int, float> is
    // constructible or not
    cout << "int(float): "
         << is_constructible<int, float>::value
         << endl;

    // Check if <int, float, float> is
    // constructible or not
    cout << "int(float, float): "
         << is_constructible<int, float, float>::value
         << endl;

    // Check if struct T is
    // constructible or not
    cout << "T: "
         << is_constructible<T>::value
         << endl;

    // Check if struct <T, int> is
    // constructible or not
    cout << "T(int): "
         << is_constructible<T, int>::value
         << endl;

    // Check if struct <T, int, int> is
    // constructible or not
    cout << "T(int, int): "
         << is_constructible<T, int, int>::value
         << endl;
    return 0;
}
```

**输出:**

```cpp
int: true
int(float): true
int(float, float): false
T: false
T(int): false
T(int, int): true

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/is _ constructionable/