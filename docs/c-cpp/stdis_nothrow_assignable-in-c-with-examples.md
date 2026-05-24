# STD::is _ northrow _ 可在 C++ 中赋值，示例

> 原文:[https://www . geesforgeks . org/stdis _ northrow _ assigned-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_nothrow_assignable-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的**STD::is _ northrow _ assigned**模板存在于**<**type _ traits**>**头文件中。C++ STL 的**STD::is _ north row _ assigned**模板用于检查 **A** 是否类型可赋值给 **B** ，这是众所周知的不抛出任何异常。如果 **A** 是可分配给 **B** 的类型，则返回布尔值 true，否则返回 false。

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template< class A, class B >
struct is_nothrow_assignable;

```

**语法:**

```cpp
std::is_assignable<A, B>::value

```

**参数:**模板**STD::is _ assigned**接受以下参数:

*   **A:** indicates that parameter B is implicitly assigned.
*   **B:** indicates the type of parameter that can be assigned to a.

**返回值:**模板**STD::is _ assigned**返回如下所示的布尔变量:

*   **true:** If type A can be assigned to type B. 。
*   **false:** If type A cannot be assigned to type B. 。

下面是用 C++ 演示**STD::is _ northrow _ assigned**模板的程序:

**程序:**

```cpp
// C++ program to illustrate
// std::is_nothrow_assignable
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare structures
struct A {
};

struct B {
    B& operator=(const A&) noexcept
    {
        return *this;
    }
    B& operator=(const B&)
    {
        return *this;
    }
};

// Declare classes
class GfG {
};

class gfg {
};

enum class AB : int { x,
                      y,
                      z };

// Driver Code
int main()
{

    cout << boolalpha;

    // Check if int& is assignable to
    // double or not
    cout << "is int = double? "
         << is_nothrow_assignable<int&,
                                  double>::value
         << endl;

    // Check if struct A is assignable to
    // srtuct A or not
    cout << "is struct A = struct A? "
         << is_nothrow_assignable<A, A>::value
         << endl;

    // Check if struct B is assignable to
    // srtuct A or not
    cout << "is class B = class A? "
         << is_nothrow_assignable<B, A>::value
         << endl;

    // Check if struct B is assignable to
    // srtuct B or not
    cout << "is class B = class B? "
         << is_nothrow_assignable<B, B>::value
         << endl;

    // Check if enum class AB is assignable
    // from class gfg or not
    cout << "is class AB = class gfg? "
         << is_nothrow_assignable<AB, gfg>::value
         << endl;

    // Check if class GfG assignable to
    // class gfg or not
    cout << "is class Gfg = class gfg? "
         << is_nothrow_assignable<GfG, gfg>::value
         << endl;
    return 0;
}
```

**输出:**

```cpp
is int = double? true
is struct A = struct A? true
is class B = class A? true
is class B = class B? false
is class AB = class gfg? false
is class Gfg = class gfg? false

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/is _ northrow _ assigned/