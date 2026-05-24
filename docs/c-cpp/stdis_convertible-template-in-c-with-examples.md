# STD::is _ convertible c++ 模板，示例

> 原文:[https://www . geesforgeks . org/stdis _ convertible-template-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_convertible-template-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的 **std::is_convertible** 模板存在于**<**type _ traits**>**头文件中。C++ STL 的 **std::is_convertible** 模板用于检查任何[数据类型](https://www.geeksforgeeks.org/data-types-in-c/) A 是否可以隐式转换为任何数据类型 b，返回真或假的布尔值。

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template< class From, class To >
struct is_convertible;

template< class From, class To >
struct is_nothrow_convertible;

```

**语法:**

```cpp
is_convertible <A*, B*>::value;

```

**参数:**取 A、B 两种数据类型为:

*   **A:** indicates the parameter to be converted.
*   **b:** indicates the implicit conversion of parameter **a** .

**返回值:**

*   **True:** If the given data type **a** is converted to data type **b** .
*   **false:** If the given data type **a** is not converted to data type **b** .

下面是用 C++ 演示 **std::is_convertible** 的程序:

**程序:**

```cpp
// C++ program to illustrate
// std::is_convertible example
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Given classes
class A {
};
class B : public A {
};
class C {
};

// Driver Code
int main()
{
    cout << boolalpha;

    // Check if class B is
    // convertible to A or not
    bool BtoA = is_convertible<B*, A*>::value;
    cout << BtoA << endl;

    // Check if class A is
    // convertible to B or not
    bool AtoB = is_convertible<A*, B*>::value;
    cout << AtoB << endl;

    // Check if class B is
    // convertible to C or not
    bool BtoC = is_convertible<B*, C*>::value;
    cout << BtoC << endl;

    // Check if int is convertible
    // to float or not
    cout << "int to float: "
         << is_convertible<int, float>::value
         << endl;

    // Check if int is convertible
    // to const int or not
    cout << "int to const int: "
         << is_convertible<int, const int>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
true
false
false
int to float: true
int to const int: true

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/is _ convertible/