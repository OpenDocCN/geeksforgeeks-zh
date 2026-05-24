# 标准::C++ 中的 add_cv 示例

> 原文:[https://www.geeksforgeeks.org/stdadd_cv-in-c-with-examples/](https://www.geeksforgeeks.org/stdadd_cv-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的 **std::add_cv** 模板存在于**T14】type _ traits>T5】头文件中。C++ STL 的 **std::add_cv** 模板用于获取具有常量和变量资格的类型 **T** 。功能 **std::is_same::value** 用于检查 **T** 是否为常量和易失性资质。**

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template< class T >
struct add_cv

```

**语法:**

```cpp
std::add_const::type

```

**参数:**模板 **std::add_cv** 接受单个参数 **T(性状类)**检查 **T** 是否常量和挥发合格。

下面是用 C++ 演示 **std::add_cv** 的程序:

**程序:**

```cpp
// C++ program to illustrate
// std::add_cv
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Driver Code
int main()
{

    // Declare variables of int, const,
    // volatile, const volatile using add_cv
    typedef add_cv<int>::type A;
    typedef add_cv<const int>::type B;
    typedef add_cv<volatile int>::type C;
    typedef add_cv<const volatile int>::type D;

    cout << boolalpha;

    // Check the type of variable declared
    // above is volatile or not

    cout << "A: "
         << is_volatile<A>::value
         << endl;

    cout << "B: "
         << is_volatile<B>::value
         << endl;

    cout << "C: "
         << is_volatile<C>::value
         << endl;

    cout
        << "D: "
        << is_volatile<D>::value
        << endl;

    return 0;
}
```

**输出:**

```cpp
typedefs of const volatile int:
A: true
B: true
C: true
D: true

```

**参考:**T2】http://www.cplusplus.com/reference/type_traits/add_cv/