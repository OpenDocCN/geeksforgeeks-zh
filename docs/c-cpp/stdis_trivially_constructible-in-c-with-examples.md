# std::在 C++ 中可以通过示例

进行简单的构造

> 原文:[https://www . geesforgeks . org/stdis _ trivaly _ constructionable-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_trivially_constructible-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的**STD::is _ trivaly _ construction**模板存在于**<**type _ traits**>**头文件中。C++ STL 的**STD::is _ trivially _ constructible**模板用于检查给定的类型 **T** 是否是带有参数集的 trivaly _ construction 类型。如果 T 是普通可构造类型，它返回布尔值 true，否则返回 false。

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template <class T, class.. Args>
struct is_trivially_constructible;

```

**语法:**

```cpp
std::is_trivially_constructible::value

```

**参数:**模板**STD::is _ trivaly _ construction**接受两个参数:

*   **T:** A data type or an array with unknown binding.
*   **args:** A list of data types representing the parameter types of the constructor form, in the same order as the constructor.

**返回值:**这个模板返回一个如下所示的布尔变量:

*   True: if type **t** is a common constructable type.
*   False: If the type **t** is not a simple constructable type.

下面是用 C/C++ 说明**标准的程序:**

**程序 1:**

```cpp
// C++ program to illustrate
// std::is_trivially_constructible
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare structures
struct Ex1 {
    std::string str;
};
struct Ex2 {
    int n;
    Ex2() = default;
};

struct A {

    // Constructor
    A(int, int){};
};

// Driver Code
int main()
{
    cout << boolalpha;

    // Check if Ex1 is a trivally
    // constructible or not
    cout << "Ex1: "
         << is_trivially_constructible<Ex1>::value
         << endl;

    // Check if struct Ex2 is a trivally
    // constructible or not
    cout << "Ex2: "
         << is_trivially_constructible<Ex2>::value
         << endl;

    // Check if A(int, float) is a trivally
    // constructible or not
    cout << "A(int, int): "
         << is_trivially_constructible<A(int, int)>::value
         << endl;
    return 0;
}
```

**输出:**

```cpp
Ex1: false
Ex2: true
A(int, int): false

```

**程序二:**

```cpp
// C++ program to illustrate
// std::is_trivially_constructible
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare structures
struct X {
};

struct Y {

    // Default Constructor
    Y() {}

    // Parameterized Constructor
    Y(const X&)
    noexcept {}
};

// Driver Code
int main()
{
    cout << boolalpha;

    // Check if int is a trivally
    // constructible or not
    cout << "int(): "
         << is_trivially_constructible<int>::value
         << endl;

    // Check if struct Y is a trivally
    // constructible or not
    cout << "Y(): "
         << is_trivially_constructible<Y>::value
         << endl;

    // Check if Y(X) is a trivally
    // constructible or not
    cout << "Y(X): "
         << is_trivially_constructible<Y, X>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
int(): true
Y(): false
Y(X): false

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/is _ trivaly _ construction/