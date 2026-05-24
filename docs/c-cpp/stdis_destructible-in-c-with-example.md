# STD::is _ destructionable 在 C++ 中，示例

> 原文:[https://www . geeksforgeeks . org/stdis _ destructible-in-c-with-example/](https://www.geeksforgeeks.org/stdis_destructible-in-c-with-example/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的**STD::is _ destruction**模板存在于**<**type _ traits**>**头文件中。C++ STL 的**STD::is _ destructive**模板用于检查 **T** 是否可销毁。一个[类](https://www.geeksforgeeks.org/c-classes-and-objects/)被称为可析构函数，它的析构函数不被删除，并且在派生类中可能是可访问的。如果 **T** 是可析构类型，则返回布尔值 true，否则返回 false。

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template< class T >
struct is_destructible;

```

**语法:**

```cpp
std::is_destructible<T>::value

```

**参数:**模板**STD::is _ destruction**接受单个参数 **T(Trait 类)**检查 **T** 是否为可破坏类型。

**返回值:**模板**STD::is _ destructionable**返回如下所示的布尔变量:

*   **true:** If type T is destructible.
*   **false:** If the type t is not destructible.

下面是用 C++ 演示**STD::is _ destructive**的程序:

**程序:**

```cpp
// C++ program to illustrate
// std::is_destructible
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare a structures
struct X {
};

struct Y {

    // Destructors
    ~Y() = delete;
};

struct Z {
    ~Z() = default;
};

struct A : Y {
};

// Driver Code
int main()
{

    cout << boolalpha;

    // Check if int is destructible
    // or not
    cout << "int is destructible? "
         << is_destructible<int>::value
         << endl;

    // Check if float is destructible
    // or not
    cout << "float is destructible? "
         << is_destructible<float>::value
         << endl;

    // Check if struct X is
    // destructible or not
    cout << "struct X is destructible? "
         << is_destructible<X>::value
         << endl;

    // Check if struct Y is
    // destructible or not
    cout << "struct Y is destructible? "
         << is_destructible<Y>::value
         << endl;

    // Check if struct Z is
    // destructible or not
    cout << "struct Z is destructible? "
         << is_destructible<Z>::value
         << endl;

    // Check if struct A is
    // destructible or not
    cout << "struct A is destructible? "
         << is_destructible<A>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
int is destructible? true
float is destructible? true
struct X is destructible? true
struct Y is destructible? false
struct Z is destructible? true
struct A is destructible? false

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/is _ destructible/