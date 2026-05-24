# STD::is _ trivaly _ move _ 可在 C++ 中赋值，示例

> 原文:[https://www . geeksforgeeks . org/stdis _ trivaly _ move _ assigned-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_trivially_move_assignable-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的**STD::is _ trivaly _ move _ attributed**模板存在于 **< type_traits >** 头文件中。C++ STL 的**STD::is _ trivaly _ move _ attributed**模板用于检查 **T** 是否为 trivaly move attributed 类型。如果 **T** 是普通移动可赋值类型，则返回布尔值 true，否则返回 false。

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template <class T>
struct is_trivially_move_assignable;

```

**语法:**

```cpp
std::is_trivially_move_assignable<T>::value

```

**参数:**模板**STD::is _ trivaly _ move _ assigned**接受单个参数 **T(性状类)**检查 **T** 是否是 trivially move assignable。

**返回值:**模板**STD::is _ trivaly _ move _ attributed**返回如下所示的布尔变量:

*   **真:**如果类型 **T** 是平凡地移动.
*   **False:** If the type **t** is not an assignable ordinary movement.

以下是在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中演示**STD::is _ trivaly _ move _ assigned**的程序:

**程序:**

```cpp
// C++ program to illustrate
// std::is_trivially_move_assignable
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare Structures
class A {
};

struct B {
    B& operator=(B&&) = delete;
};

// Driver Code
int main()
{

    cout << boolalpha;

    cout << "int is_trivially_move_assignable? "
         << is_trivially_move_assignable<int>::value
         << endl;

    cout << "A is_trivially_move_assignable? "
         << is_trivially_move_assignable<A>::value
         << endl;

    cout << "B is_trivially_move_assignable? "
         << is_trivially_move_assignable<B>::value
         << endl;

    cout << "int[2] is triviallay move assignable? "
         << is_trivially_move_assignable<int[2]>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
int is_trivially_move_assignable? true
A is_trivially_move_assignable? true
B is_trivially_move_assignable? false
int[2] is triviallay move assignable? false

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/is _ trivaly _ move _ assigned/