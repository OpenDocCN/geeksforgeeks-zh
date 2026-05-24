# std::is_member_pointer 用 C++ 举例

> 原文:[https://www . geesforgeks . org/stdis _ member _ pointer-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_member_pointer-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的 **std::is_member_pointer** 模板存在于**<**type _ traits**>**头文件中。C++ STL 的 **std::is_member_pointer** 模板用于检查 T 是否是非静态成员的指针。如果 **T** 是指向非静态成员类型的指针，则返回布尔值 true，否则返回 false。

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template<class T>
struct is_member_pointer
     : std::integral_constant < bool,
       is_member_object_pointer<T>::value 
    || is_member_function_pointer<T>::value> {};

```

**语法:**

```cpp
std::is_member_pointer::value

```

**参数:**模板 s **td::is_member_pointer** 接受单个参数 **T(Trait 类)**检查 **T** 是否指向非静态成员。

**返回值:**该模板返回如下所示的布尔变量:

*   True: if the type **t** is a pointer to a non-static member.
*   True: if the type **t** is not a pointer to a non-static member.

下面是用 C/C++ 说明**标准::is_member_pointer 模板**的程序:

**程序:**

```cpp
// C++ program to illustrate
// std::is_member_pointer
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Driver Code
int main()
{

    // Empty Class GFG
    class GFG {
    };

    // Check if GFG::* is a member
    // pointer or not
    bool a = is_member_pointer<int(GFG::*)>::value;
    if (a) {
        cout << "GFG::* is a Member Pointer!"
             << endl;
    }
    else {
        cout << "GFG::* is not a Member Pointer!"
             << endl;
    }

    // Check if int is a member
    // pointer or not
    a = is_member_pointer<int(int)>::value;
    if (a) {
        cout << "int is a Member Pointer!"
             << endl;
    }
    else {
        cout << "int is not a Member Pointer!"
             << endl;
    }

    return 0;
}
```

**输出:**

```cpp
GFG::* is a Member Pointer!
int is not a Member Pointer!

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/is _ member _ pointer/