# STD::is _ copy _ 可在 C++ 中构造，示例

> 原文:[https://www . geesforgeks . org/stdis _ copy _ constructionable-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_copy_constructible-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的**STD::is _ copy _ construction**模板存在于**<**type _ traits**>**头文件中。C++ STL 的**STD::is _ copy _ construction**模板用于检查 **T** 是否可复制构建。如果 **T** 是可复制构造类型，则返回布尔值 true，否则返回 false。

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template <class T> struct is_copy_constructible;

```

**语法:**

```cpp
std::is_copy_constructible <int> ::value
std::is_copy_constructible>class T> ::value

```

**参数:**该模板接受单个参数 **T(性状类)**检查 T 是否可复制构建。

**返回值:**该模板返回如下所示的布尔变量:

*   **true:** If the type **t** is replicable.
*   **false:** If the type **t** is not replicable. /li >

下面的程序说明了 C/C++ 中的标准::is _ copy _ constructiblev 模板:

**程序:**

```cpp
// C++ program to illustrate
// std::is_copy_constructible example
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare structures
struct B {
};
struct A {
    A& operator=(A&) = delete;
};

// Driver Code
int main()
{
    cout << boolalpha;

    // Check that if char is copy
    // constructible or not
    cout << "char: "
         << is_copy_constructible<char>::value
         << endl;

    // Check that if int is copy
    // constructible or not
    cout << "int: "
         << is_copy_constructible<int>::value
         << endl;

    // Check that if int[2] is copy
    // constructible or not
    cout << "int[2]: "
         << is_copy_constructible<int[2]>::value
         << endl;

    // Check that if struct A is copy
    // constructible or not
    cout << "struct A: "
         << is_copy_constructible<A>::value
         << endl;

    // Check that if struct B is copy
    // constructible or not
    cout << "struct B: "
         << is_copy_constructible<B>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
char: true
int: true
int[2]: false
struct A: true
struct B: true

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/is _ copy _ constructionable/