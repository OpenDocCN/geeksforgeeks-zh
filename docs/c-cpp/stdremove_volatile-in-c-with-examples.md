# std::remove_volatile 在 C++ 中使用示例

> 原文:[https://www . geeksforgeeks . org/STD remove _ volatile-in-c-with-examples/](https://www.geeksforgeeks.org/stdremove_volatile-in-c-with-examples/)

C++ STL 的 **std::remove_volatile** 模板存在于< type_traits >头文件中。使用 [C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的 **std::remove_volatile** 模板获取无 volatile 资质的 **T** 。如果 **T** 没有 volatile qualified，则返回布尔值 true，否则返回 false。下面是相同的语法:

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template <class <T>
struct remove_volatile;

```

**语法:**

```cpp
std::remove_volatile::value

```

**参数:**模板**STD::rme over _ volatile**接受单个参数 **T(性状类)**检查 **T** 是否无挥发合格。

**返回值:**模板 **std::remove_volatile** 返回布尔值:

**True:**

 **T** 

*   **False:** If the type **t** is band volatilization qualified.

下面是在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中演示 **std::remove_volatile** 的程序:

**程序 1:**

```cpp
// C++ program to illustrate
// std::remove_volatile
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Driver Code
int main()
{

    // Declare variable of type
    // volatile (int, const int, const int*,
    // int * const and const int&)
    typedef remove_volatile<int>::type A;
    typedef remove_volatile<volatile int>::type B;
    typedef remove_volatile<int* volatile>::type C;
    typedef remove_volatile<volatile int*>::type D;
    typedef remove_volatile<volatile int&>::type E;

    cout << boolalpha;

    // Checking the non-volatileness
    // of the above declared variable
    cout << "checking Non-volatileness:"
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
checking Non-volatileness:
A: false
B: false
C: false
D: false
E: false

```

**程序二:**

```cpp
// C++ program to illustrate
// std::remove_volatile
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
    typedef remove_cv<float>::type a;
    typedef remove_cv<char* const>::type b;
    typedef remove_cv<const char*>::type c;

    cout << boolalpha;

    // Checking the non-volatileness
    // of the above declared variable
    cout << "checking Non-volatileness:"
         << endl;

    cout << "A: "
         << is_volatile<A>::value
         << endl;

    cout << "B: "
         << is_volatile<B>::value
         << endl;

    cout << "C: "
         << is_volatile<a>::value
         << endl;

    cout << "D: "
         << is_volatile<b>::value
         << endl;

    cout << "E: "
         << is_volatile<c>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
checking Non-volatileness:
A: true
B: true
C: false
D: false
E: false

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/remove _ volatile/