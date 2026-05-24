# std::在 C++ 中是可普通销毁的，示例

> 原文:[https://www . geesforgeks . org/stdis _ trivaly _ destructible-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_trivially_destructible-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的**STD::is _ trivaly _ destruction**模板存在于**<**type _ traits**>**头文件中。C++ STL 的**STD::is _ trivy _ denstructable**模板用于检查 **T** 是否为 trivially destructible 类型。如果 **T** 是普通可析构类型，则返回布尔值 true，否则返回 false。

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template <class T>
struct is_trivially_destructible;

```

**语法:**

```cpp
std::is_trivially_destructible<T>::value

```

**参数:**模板**STD::is _ trivy _ destruction**接受单个参数 **T(Trait 类)**检查 **T** 是否为 trivially destructible 类型。

**返回值:**这个模板返回一个如下所示的布尔变量:

*   True: If the type **t** is an ordinary destructible type.
*   False: If the type **t** is not an ordinary destructible type.

下面是用 C/C++ 说明**标准的程序:**

**程序 1:**

```cpp
// C++ program to illustrate
// std::is_trivially_destructible
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare structures
struct Y {
    // Constructor
    Y(int, int){};
};

struct X {

    // Destructor
    ~X() noexcept(false)
    {
    }
};

struct Z {
    ~Z() = default;
};

// Declare classes
class A {
    virtual void fn() {}
};

// Driver Code
int main()
{

    cout << boolalpha;

    // Check if int is trivially
    // destructable or not
    cout << "int: "
         << is_trivially_destructible<int>::value
         << endl;

    // Check if struct X is trivially
    // destructable or not
    cout << "struct X: "
         << is_trivially_destructible<X>::value
         << endl;

    // Check if struct Y is trivially
    // destructable or not
    cout << "struct Y: "
         << is_trivially_destructible<Y>::value
         << endl;

    // Check if struct Z is trivially
    // destructable or not
    cout << "struct Z: "
         << is_trivially_destructible<Z>::value
         << endl;

    // Check if class A is trivially
    // destructable or not
    cout << "class A: "
         << is_trivially_destructible<A>::value
         << endl;

    // Check if constructor Y(int, int) is
    // trivially destructable or not
    cout << "Constructor Y(int, int): "
         << is_trivially_destructible<Y(int, int)>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
int: true
struct X: false
struct Y: true
struct Z: true
class A: true
Constructor Y(int, int): false

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/is _ trivaly _ destructive/