# 标准::is _ move _ 可赋值 C++ 示例

> 原文:[https://www . geesforgeks . org/stdis _ move _ assigned-c-with-examples/](https://www.geeksforgeeks.org/stdis_move_assignable-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的**STD::is _ move _ assigned**模板存在于**<**type _ traits**>**头文件中。C++ STL 的**STD::is _ move _ assigned**模板用于检查 **T** 是否为移动可赋值类型(可赋同类型的右值引用)。如果 **T** 是移动可赋值类型，则返回布尔值 true，否则返回 false。

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template <class T>
struct is_move_assignable;

```

**语法:**

```cpp
std::is_move_assignable<T>::value

```

**参数:**模板**STD::is _ move _ assigned**接受单个参数 **T(性状类)**检查 **T** 是否为 move assignable。

**返回值:**该模板返回如下所示的布尔变量:

*   True: if the type **t** is a mobile distributable type.
*   False: If the type **t** is not a mobile distributable type.

下面是用 C/C++ 说明**标准::is _ move _ 可赋值模板**的程序:

**程序:**

```cpp
// C++ program to illustrate
// std::is_move_assignable
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare structures
struct A {
};

struct B {
    B& operator=(B&) = delete;
};

struct C {
    ~C() = delete;
};

// Driver Code
int main()
{

    cout << boolalpha;

    // Check if int is move
    // assignable or not
    cout << "int: "
         << is_move_assignable<int>::value
         << endl;

    // Check if struct A is move
    // assignable or not
    cout << "struct A: "
         << is_move_assignable<A>::value
         << endl;

    // Check if struct B is move
    // assignable or not
    cout << "struct B: "
         << is_move_assignable<B>::value
         << endl;

    // Check if struct C is move
    // assignable or not
    cout << "struct C: "
         << is_move_assignable<C>::value
         << endl;

    // Declare an map
    unordered_multimap<int, string> m;
    m.insert({ 1, "GfG" });

    // Check if map m is move
    // assignable or not?
    cout << "Map m: "
         << is_move_assignable<decltype(*m.begin())>::value;

    return 0;
}
```

**输出:**

```cpp
int: true
struct A: true
struct B: false
struct C: true
Map m: true

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/is _ move _ assigned/