# STD::is _ default _ 可在 C++ 中构造，示例

> 原文:[https://www . geesforgeks . org/stdis _ default _ constructionable-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_default_constructible-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的**STD::is _ default _ construction**模板存在于**<**type _ traits**>**头文件中。C++ STL 的**STD::is _ default _ construction**模板用于检查 **T** 是否默认可建。默认构造函数可以在没有参数或初始值的情况下构造。如果 **T** 是默认可构造类型，则返回布尔值 true，否则返回 false。

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template <class T> 
struct is_default_constructible;

```

**语法:**

```cpp
std::is_default_constructible>class T> ::value

```

**参数:**模板**STD::is _ default _ construction**接受单个参数 **T(Trait 类)**检查 **T** 是否为默认可构造类型。

**返回值:**该模板返回如下所示的布尔变量:

*   **true:** If the type **t** is constructable by default.
*   **false:** If the type **t** is not constructable by default.

下面是用 C/C++ 说明**标准::is _ default _ construction**模板的程序:

**程序:**

```cpp
// C++ program to illustrate
// std::is_default_constructible
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare structures
struct A {
};

struct B {
    int n;
    B() = default;
};

// Class
class classA {
    ~classA() = delete;
};

// Inherited class
class classB : classA {
};

// Driver Code
int main()
{
    cout << boolalpha;

    // Check if int is default constructible?
    cout << "int : "
         << is_default_constructible<int>::value
         << endl;

    // Check if struct A is default constructible?
    cout << "struct A: "
         << is_default_constructible<A>::value
         << endl;

    // Check if struct B is default constructible?
    cout << "struct B: "
         << is_default_constructible<B>::value
         << endl;

    // Check if classA is default constructible?
    cout << "classA: "
         << is_default_constructible<classA>::value
         << endl;

    // Check if classB is default constructible?
    cout << "classB: "
         << is_default_constructible<classB>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
int : true
struct A: true
struct B: true
classA: false
classB: false

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/is _ default _ constructionable/