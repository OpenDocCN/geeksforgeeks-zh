# 标准::C++ 中的 add_lvalue_reference 附带示例

> 原文:[https://www . geesforgeks . org/stdadd _ lvalue _ reference-in-c-with-examples/](https://www.geeksforgeeks.org/stdadd_lvalue_reference-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的**标准::add_lvalue_reference** 模板存在于 **< type_traits >** 头文件中。C++ STL 的**STD::add _ lvalue _ reference**模板用来获取引用 **T** 类型的 **lvalue reference** 类型。一个**左值**引用是通过在某个类型后放置一个 **' & '** 而形成的。右值引用是通过在某个类型后放置一个 **' & & '** 而形成的。左值不能将(**非常数**)左值引用绑定到右值。
模板**检查**标准::add_lvalue_reference** 标准::is_lvalue_reference::value** 。

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template< class T >
struct add_lvalue_reference

```

**语法:**

```cpp
std::is_lvalue_reference<T>::value

```

**参数:**模板**STD::add _ lvalue _ reference**接受单个参数 **T(性状类)**

下面是在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中演示**STD::add _ lvalue _ reference**的程序:

**程序 1:**

```cpp
// C++ program to illustrate
// std::add_lvalue_reference
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Driver Code
int main()
{

    // Declare lvalue of type int, int&,
    // int&& and int*
    typedef add_lvalue_reference<int const&>::type A;
    typedef add_lvalue_reference<int&>::type B;
    typedef add_lvalue_reference<int&&>::type C;
    typedef add_lvalue_reference<int&>::type D;

    cout << std::boolalpha;

    // Check if A is int const& or not
    cout << "A: " << is_same<int const&, A>::value
         << endl;

    // Check if B is int* or not
    cout << "B: " << is_same<int*, B>::value
         << endl;

    // Check if C is int& or not
    cout << "C: " << is_same<int&, C>::value
         << endl;

    // Check if C is int && or not
    cout << "D: " << is_same<int&&, D>::value
         << endl;

    return 0;
}
```

**Output:**

```cpp
A: true
B: false
C: true
D: false

```

**程序 2:**

```cpp
// C++ program to illustrate
// std::add_lvalue_reference
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Driver Code
int main()
{

    // Declare lvalue using typename
    using a = int;
    using b = float;
    using lref
        = typename add_lvalue_reference<a>::type;
    using rref
        = typename add_rvalue_reference<b>::type;

    cout << std::boolalpha;

    // Check if the above declaration
    // are correct or not
    cout << "is int is lvalue? "
         << is_lvalue_reference<a>::value
         << '\n';

    cout << "is lref is lvalue? "
         << is_lvalue_reference<lref>::value
         << '\n';

    cout << "is float is lvalue? "
         << is_rvalue_reference<b>::value
         << '\n';
    return 0;
}
```

**Output:**

```cpp
is int is lvalue? false
is lref is lvalue? true
is float is lvalue? false

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/add _ lvalue _ Reference/