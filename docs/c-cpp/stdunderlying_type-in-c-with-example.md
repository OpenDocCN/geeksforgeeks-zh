# 标准::C++ 中的基础 _ 类型，示例

> 原文:[https://www . geeksforgeeks . org/STD believe _ type-in-c-with-example/](https://www.geeksforgeeks.org/stdunderlying_type-in-c-with-example/)

C++ STL 的**标准::底层 _ 类型**模板存在于<类型 _ 特征>头文件中。 [C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的**STD::under _ type**模板用于获取枚举类型 **T** 的底层类型。

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template <class T>
struct underlying_type;

```

**语法:**

```cpp
std::underlying_type<class T>::value

```

**参数:**模板 **std::underlying_type** 接受单个参数 **T(Trait 类)**。

**返回值:**模板 **std::underlying_type** 返回枚举类型 t 的底层类型

以下是在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中演示**标准::底层 _ 类型**的程序:

**程序:**

```cpp
// C++ program to illustrate
// std::underlying_type
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// ENUM Class GFG
enum GFG {};

// Class gfg
enum class gfg : int {};

// Driver Code
int main()
{
    bool GFG1
        = is_same<unsigned,
                  typename underlying_type<GFG>::type>::value;

    bool gfg1
        = is_same<int,
                  typename underlying_type<gfg>::type>::value;

    cout << "underlying type for 'GFG' is "
         << (GFG1 ? "unsigned" : "non-unsigned")
         << endl;

    cout << "underlying type for 'gfg' is "
         << (gfg1 ? "int" : "non-int")
         << endl;

    return 0;
}
```

**输出:**

```cpp
underlying type for 'GFG' is unsigned
underlying type for 'gfg' is int

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/underlying _ type/