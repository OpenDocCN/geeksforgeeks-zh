# STD::is _ 同 C++ 模板，示例

> 原文:[https://www . geesforgeks . org/stdis _ same-template-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_same-template-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的 **std::is_same** 模板存在于**<**type _ traits**>**头文件中。C++ STL 的 **std::is_same** 模板用于检查类型 **A** 是否与类型 **B** 相同。如果两者相同，则返回布尔值 true，否则返回 false。

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template <class A, class B>
struct is_same

template <class A, class B>
inline constexpr 
       bool is_same_v
         = is_same<A, B>::value

```

**语法:**

```cpp
std::is_same<A, B>::value

```

**参数:**这个 **std::is_same** 模板接受以下参数:

**A:**

*   **B:** It stands for the second type.

**返回值:**模板 **std::is_same** 返回如下所示的布尔变量:

*   **true:** If type **a** is the same as type **b** .
*   **False:** If type **a** is different from type **b** .

下面是在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中演示 **std::is_same** 的程序:

**程序:**

```cpp
// C++ program to illustrate std::is_same
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Driver Code
int main()
{

    cout << boolalpha;

    cout << "is int & int32_t is same? "
         << is_same<int, int32_t>::value
         << endl;

    cout << "is int & int64_t is same? "
         << is_same<int, int64_t>::value
         << endl;

    cout << "is float & int32_t is same? "
         << is_same<float, int32_t>::value
         << endl;

    cout << "is int & int is same? "
         << is_same<int, int>::value << endl;
    cout << "is int & unsigned int is same? "
         << is_same<int, unsigned int>::value
         << endl;

    cout << "is int & signed int is same? "
         << is_same<int, signed int>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
is int & int32_t is same? true
is int & int64_t is same? false
is float & int32_t is same? false
is int & int is same? true
is int & unsigned int is same? false
is int & signed int is same? true

```

**程序二:**

```cpp
// C++ program to illustrate std::is_same
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

typedef int integer_type;

// Declare structures
struct A {
    int x, y;
};
struct B {
    int x, y;
};
typedef A C;

// Driver Code
int main()
{

    cout << boolalpha;

    cout << "is_same:" << endl;
    cout << "int, const int is_same: "
         << is_same<int, const int>::value
         << endl;

    cout << "int, integer_type is_same: "
         << is_same<int, integer_type>::value
         << endl;

    cout << "A, B is_same: "
         << is_same<A, B>::value
         << endl;

    cout << "A, C is_same: "
         << is_same<A, C>::value
         << endl;

    cout << "signed char, int8_t is_same: "
         << is_same<signed char, int8_t>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
is_same:
int, const int is_same: false
int, integer_type is_same: true
A, B is_same: false
A, C is_same: true
signed char, int8_t is_same: true

```

**参考:**T2】http://www.cplusplus.com/reference/type_traits/is_same/