# 标准::C++ 中的 add_const 示例

> 原文:[https://www . geesforgeks . org/stdadd _ const-in-c-with-examples/](https://www.geeksforgeeks.org/stdadd_const-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的 **std::add_const** 模板存在于**<**type _ traits**>**头文件中。C++ STL 的 **std::add_const** 模板用于获取具有 const 资质的类型 **T** 。 **std::is_volatile** 用于检查 **T** 型常量是否合格。

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template < class T >
struct add_const;

```

**语法:**

```cpp
std::add_const<T>::value

```

**参数:**模板 **std::add_const** 接受单个参数 **T(性状类)**，用于声明类型 **T** 为合格的 const。

下面是用 C++ 演示 **std::add_const:** 的程序:

**程序:**

```cpp
// C++ program to illustrate
// std::add_const
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Driver Code
int main()
{

    // Declare variable of type
    // int, const int, const int*,
    // int * const and const int&
    typedef add_const<int>::type A;
    typedef add_const<const int>::type B;
    typedef add_const<const int*>::type C;
    typedef add_const<int* const>::type D;
    typedef add_const<const int&>::type E;

    cout << std::boolalpha;

    // Checking const of the above
    // declared variables
    cout << "A is const int? "
         << is_same<const int, A>::value
         << endl;

    cout << "B is const int? "
         << is_same<const int, B>::value
         << endl;

    cout << "C is const int? "
         << is_same<const int, C>::value
         << endl;

    cout << "D is const int? "
         << is_same<const int, D>::value
         << endl;

    std::cout << "E is const int? "
              << is_same<const int, E>::value
              << endl;

    return 0;
}
```

**输出:**

```cpp
A is const int? true
B is const int? true
C is const int? false
D is const int? false
E is const int? false

```

**参考:**T2】http://www.cplusplus.com/reference/type_traits/add_const/