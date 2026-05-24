# STD::is _ member _ function _ pointer c++ 中的模板，带示例

> 原文:[https://www . geesforgeks . org/stdis _ member _ function _ pointer-template-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_member_function_pointer-template-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的**STD::is _ member _ function _ pointer**模板存在于< [type_traits](https://www.geeksforgeeks.org/tag/cpp-type_traits/) >头文件中。 [C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的**STD::is _ member _ function _ pointer**模板用于检查 **T** 是否是非静态成员函数的指针。如果 **T** 是指向非静态成员函数的指针，则返回布尔值 true，否则返回 false。

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template <class T>
struct is_member_function_pointer;

```

**语法:**

```cpp
std::is_member_function_pointer::value 

```

**参数:**模板**STD::is _ member _ function _ pointer**接受单个参数 **T(Trait 类)**检查 **T** 是否是指向非静态成员函数的指针。

**返回值:**此模板**STD::is _ member _ object _ pointer**返回如下所示的布尔变量:

**True:**

 **T** 

*   **false:** If the type **t** is not a pointer to a non-static member function type.

下面是在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中演示**STD::is _ member _ function _ pointer**的程序:

**程序 1:**

```cpp
// C++ program to illustrate
// std::is_member_function_pointer
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare a structure
class GFG {

public:
    int gfg;
};

class A {
};

// Driver Code
int main()
{

    // Object to class GFG
    int GFG::*pt = &GFG::gfg;
    cout << boolalpha;

    // Check if GFG* is a member function
    // pointer or not
    cout << "GFG*: "
         << is_member_function_pointer<GFG*>::value
         << endl;

    // Check if int GFG::* is a member
    // function pointer or not
    cout << "int GFG::* "
         << is_member_function_pointer<int GFG::*>::value
         << endl;

    // Check if int A::* is a member
    // function pointer or not
    cout << "int A::* "
         << is_member_function_pointer<int A::*>::value
         << endl;

    // Check if int A::*() is a member
    // function pointer or not
    cout << "int A::*() "
         << is_member_function_pointer<int (A::*)()>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
GFG*: false
int GFG::* false
int A::* false
int A::*() true

```

**程序二:**

```cpp
// C++ program to illustrate
// std::is_member_function_pointer
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare a structure
struct A {
    void fn(){};
};

struct B {
    int x;
};

// Driver Code
int main()
{
    void (A::*pt)() = &A::fn;
    cout << boolalpha;

    cout << "A*: "
         << is_member_function_pointer<A*>::value
         << endl;

    cout << "void(A::*)(): "
         << is_member_function_pointer<void (A::*)()>::value
         << endl;

    cout << "B*: "
         << is_member_function_pointer<B*>::value
         << endl;

    cout << "void(B::*)(): "
         << is_member_function_pointer<void (B::*)()>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
A*: false
void(A::*)(): true
B*: false
void(B::*)(): true

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/is _ member _ function _ pointer/