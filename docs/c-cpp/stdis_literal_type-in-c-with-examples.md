# std::is_literal_type 在 C++ 中带有示例

> 原文:[https://www . geesforgeks . org/stdis _ literal _ type-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_literal_type-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的 **std::is_literal_type** 模板存在于**<**type _ traits**>**头文件中。C++ STL 的 **std::is_literal_type** 模板用于检查 **T** 是否为文字类型。如果 **T** 是文字类型，则返回布尔值 true，否则返回 false。

**头文件:**

```cpp
#include<type_traits>

```

**模板:**

```cpp
template< class T >
struct is_literal_type;

```

**语法:**

```cpp
std::is_literal_type::value

```

**参数:**模板 **std::is_literal_type** 接受单个参数 **T(Trait 类)**检查 **T** 是否为 literal 类型。

**返回值:**模板 **std::is_literal_type** 返回如下所示的布尔变量:

*   **true:** If type t is a text type.
*   **false:** If the type t is not literal.

下面是用 C/C++ 演示 **std::is_literal_type:** 的程序:

**程序:**

```cpp
// C++ program to illustrate
// std::is_literal_type
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare Classes
class X {
};

class Y {

    // Destructor
    ~Y() {}
};

// Declare structures
struct A {
    int m;
};

struct B {
    virtual ~B();
};

// Driver Code
int main()
{

    cout << boolalpha;

    // Check if int is literal type?
    cout << "int: "
         << is_literal_type<int>::value
         << endl;

    // Check if class X is literal type?
    cout << "class X: "
         << is_literal_type<X>::value
         << endl;

    // Check if class Y is literal type?
    cout << "class Y: "
         << is_literal_type<Y>::value
         << endl;

    // Check if int* is literal type?
    cout << "int*: "
         << is_literal_type<int*>::value
         << endl;

    // Check if struct A is literal type?
    cout << "struct A: "
         << is_literal_type<A>::value
         << endl;

    // Check if struct B is literal type?
    cout << "struct B: "
         << is_literal_type<B>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
int: true
class X: true
class Y: false
int*: true
struct A: true
struct B: false

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/is _ literal _ type/