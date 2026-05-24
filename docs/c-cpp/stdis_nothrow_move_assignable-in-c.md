# STD::is _ northrow _ move _ 可在 C++ 中赋值

> 原文:[https://www . geesforgeks . org/stdis _ northrow _ move _ assigned-in-c/](https://www.geeksforgeeks.org/stdis_nothrow_move_assignable-in-c/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的**STD::is _ northrow _ move _ attributed**模板存在于**<**type _ traits**>**头文件中。C++ STL 的**STD::is _ north row _ move _ attributed**模板用于检查 **T** 是否是一个移动可赋值类型，这是众所周知的不抛出任何异常。如果 **T** 是移动可赋值类型，则返回布尔值 true，否则返回 false。

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template< class T >
struct is_move_assignable;

```

**语法:**

```cpp
std::is_move_assignable<T>::value 

```

**参数:**模板**STD::is _ north row _ move _ assigned**接受单个参数 **T(Trait 类)**检查 **T** 是否为 move assignable，无抛出异常。

**返回值:**模板**STD::is _ northrow _ move _ assigned**返回如下所示的布尔变量:

*   **真:**如果类型 T 是移动可分配类型。
*   **False:** If T type is not mobile distributable type.

下面是演示**标准的程序:**

**程序:**

```cpp
// C++ program to illustrate
// std::is_nothrow_move_assignable
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare structures
struct A {
};

struct B {
    B& operator=(B&) = delete;
};

struct Ex1 {
    Ex1() {}
    Ex1(Ex1&&)
    {
        cout << "Throwing move constructor!";
    }
    Ex1(const Ex1&)
    {
        cout << "Throwing copy constructor!";
    }
};

struct Ex2 {
    Ex2() {}
    Ex2(Ex2&&) noexcept
    {
        cout << "Non-throwing move constructor!";
    }
    Ex2(const Ex2&) noexcept
    {
        cout << "Non-throwing copy constructor!";
    }
};

// Driver Code
int main()
{
    cout << boolalpha;

    // Check if int is a move
    // assignable or not
    cout << "int: "
         << is_nothrow_move_assignable<int>::value
         << endl;

    // Check if struct A is a move
    // assignable or not
    cout << "struct A: "
         << is_nothrow_move_assignable<A>::value
         << endl;

    // Check if struct B is a move
    // assignable or not
    cout << "struct B: "
         << is_nothrow_move_assignable<B>::value
         << endl;

    // Check if struct Ex1 is a move
    // assignable or not
    cout << "struct Ex1: "
         << is_nothrow_move_assignable<Ex1>::value
         << endl;

    // Check if struct Ex2 is a move
    // assignable or not
    cout << "struct Ex2: "
         << is_nothrow_move_assignable<Ex2>::value
         << endl;
    return 0;
}
```

**输出:**

```cpp
int: true
struct A: true
struct B: false
struct Ex1: false
struct Ex2: false

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/is _ northrow _ move _ assigned/