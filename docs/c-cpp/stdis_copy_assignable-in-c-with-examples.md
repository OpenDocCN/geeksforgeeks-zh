# STD::is _ copy _ 可在 C++ 中赋值，示例

> 原文:[https://www . geesforgeks . org/stdis _ copy _ assigned-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_copy_assignable-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的**STD::is _ copy _ assigned**模板存在于**<**type _ traits**>**头文件中。C++ STL 的**STD::is _ copy _ assigned**模板用于检查 **T** 是否可进行副本赋值。如果 **T** 是可复制赋值类型，则返回布尔值 true，否则返回 false。

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template <class T>
struct is_copy_assignable;

```

**语法:**

```cpp
std::is_copy_assignable >class T> ::value

```

**参数:**模板**STD::is _ copy _ assigned**接受单个参数 **T(Trait 类)**检查 **T** 是否为可复制赋值类型。

**返回值:**该模板返回如下所示的布尔变量:

*   **True:** If the type **t** is a replicable assignable type.
*   **False:** If the type **t** is not a replica distributable type.

下面是用 C/C++ 说明**标准::is _ copy _ 可赋值**模板的程序:

**程序:**

```cpp
// C++ program to illustrate
// std::is_copy_assignable example
#include <bits/stdc++.h>
#include <type_traits>

using namespace std;

// Declare structures
struct A {
};

struct B {
    B& operator=(const B&) = delete;
};

struct C {
    C(C&&) {}
};

// Driver Code
int main()
{

    cout << boolalpha;

    // Check if char is_copy_assignable?
    cout << "char: "
         << is_copy_assignable<char>::value
         << endl;

    // Check if struct A is_copy_assignable?
    cout << "struct A: "
         << is_copy_assignable<A>::value
         << endl;

    // Check if struct B is_copy_assignable?
    cout << "struct B: "
         << is_copy_assignable<B>::value
         << endl;

    // Check if struct C is_copy_assignable?
    cout << "struct C: "
         << is_copy_assignable<C>::value
         << endl;

    // Check if int[2] is_copy_assignable?
    cout << "int[2]: "
         << is_copy_assignable<int[2]>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
char: true
struct A: true
struct B: false
struct C: false
int[2]: false

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/is _ copy _ assigned/