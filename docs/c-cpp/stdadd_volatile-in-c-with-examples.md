# std::add_volatile 用 C++ 举例

> 原文:[https://www . geeksforgeeks . org/stdadd _ volatile-in-c-with-examples/](https://www.geeksforgeeks.org/stdadd_volatile-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的 **std::add_volatile** 模板存在于**<**type _ traits**>**头文件中。C++ STL 的 **std::add_volatile** 模板用来获取具有 volatile 资质的类型 **T** 。功能 **std::is_volatile** 用于检查类型 **T** 是否挥发合格。

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template < class T >
struct add_volatile;

```

**语法:**

```cpp
std::add_volatile<T>::value

```

**参数:**模板 **std::add_volatile** 接受单个参数 **T(Trait 类)**，用于获取具有 volatile 资质的类型 **T** 。

下面是用 C++ 演示 **std::add_volatile:** 的程序:

**程序:**

```cpp
// C++ program to illustrate
// std::add_volatile
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Driver Code
int main()
{

    // Declare variable of type
    // volatile (int, const int, const int*,
    // int * const and const int&)
    typedef add_volatile<int>::type A;
    typedef add_volatile<volatile int>::type B;
    typedef add_volatile<int* volatile>::type C;
    typedef add_volatile<volatile int*>::type D;
    typedef add_volatile<volatile int&>::type E;

    cout << boolalpha;

    // Checking the volatileness of
    // the above declared variable
    cout << "checking volatileness:"
         << endl;

    cout << "A: "
         << is_volatile<A>::value
         << endl;

    cout << "B: "
         << is_volatile<B>::value
         << endl;

    cout << "C: "
         << is_volatile<C>::value
         << endl;

    cout << "D: "
         << is_volatile<D>::value
         << endl;

    cout << "E: "
         << is_volatile<E>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
checking volatileness:
A: true
B: true
C: true
D: true
E: false

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/add _ volatile/