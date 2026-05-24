# STD::is _ trivaly _ move _ 可在 C++ 中构造，示例

> 原文:[https://www . geesforgeks . org/stdis _ trivaly _ move _ constructionable-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_trivially_move_constructible-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的**STD::is _ trivaly _ move _ construction**模板存在于**T12】type _ traits>**头文件中。C++ STL 的**STD::is _ trivy _ move _ construction**模板用于检查 **T** 是否为 trivially move constructibe。如果 **T** 是普通移动可构造类型，则返回布尔值 true，否则返回 false。

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template< class T >
struct is_trivially_move_constructible;

```

**语法:**

```cpp
std::is_trivially_move_constructible<T>::value

```

**参数:**模板**STD::is _ trivy _ move _ construction**接受单个参数 **T(Trait 类)**检查 **T** 是否为 trivially move constructible 类型。

**返回值:**模板**STD::is _ trivially _ move _ constructible**返回如下所示的布尔变量:

*   **真:**如果类型 **T** 是一个 trivaly _ move _ construction .
*   **False:** If the type **t** is not a configurable ordinary action.

下面是用 C++ 演示**STD::is _ trivaly _ move _ construction**的程序:

**程序 1:**

```cpp
// C++ program to demonstrate
// std::is_trivially_move_constructible
#include <iostream>
#include <type_traits>
using namespace std;

// Declaration of classes
class A {
};

class B {
    B() {}
};

enum class C : int { x,
                     y,
                     z };

class D {
    int v1;
    double v2;

public:
    D(int n)
        : v1(n), v2()
    {
    }
    D(int n, double f)
    noexcept : v1(n), v2(f) {}
};

int main()
{
    cout << boolalpha;

    // Check if int is trivially
    // move constructible or not
    cout << "int: "
         << is_trivially_move_constructible<int>::value
         << endl;

    // Check if class A is trivially
    // move constructible or not
    cout << "class A: "
         << is_trivially_move_constructible<A>::value
         << endl;

    // Check if class B is trivially
    // move constructible or not
    cout << "class B: "
         << is_trivially_move_constructible<B>::value
         << endl;

    // Check if enum class C is trivially
    // move constructible or not
    cout << "enum class C: "
         << is_trivially_move_constructible<C>::value
         << endl;

    // Check if class D is trivially
    // move constructible or not
    std::cout << "class D: "
              << is_trivially_move_constructible<D>::value
              << endl;
    return 0;
}
```

**输出:**

```cpp
int: true
class A: true
class B: true
enum class C: true
class D: true

```

**程序二:**

```cpp
// C++ program to demonstrate
// std::is_trivially_move_constructible
#include <iostream>
#include <type_traits>
using namespace std;

// Declare structures
struct Ex1 {
    Ex1() {}
    Ex1(Ex1&&)
    {
        cout << "Throwing move constructor!";
    }
    Ex1(const Ex1&)
    {
        cout << "Throwing copy constructor!";
    }
};

struct Ex2 {
    Ex2() {}
    Ex2(Ex2&&) noexcept
    {
        cout << "Non-throwing move constructor!";
    }
    Ex2(const Ex2&) noexcept
    {
        cout << "Non-throwing copy constructor!";
    }
};

// Driver Code
int main()
{
    cout << boolalpha;

    // Check if struct Ex1 is move
    // constructible or not
    cout << "Ex1 is move-constructible? "
         << is_move_constructible<Ex1>::value
         << '\n';

    // Check if struct Ex1 is trivially
    // move constructible or not
    cout << "Ex1 is trivially move-constructible? "
         << is_trivially_move_constructible<Ex1>::value
         << '\n';

    // Check if struct Ex2 is trivially
    // move constructible or not
    cout << "Ex2 is trivially move-constructible? "
         << is_trivially_move_constructible<Ex2>::value
         << '\n';
}
```

**输出:**

```cpp
Ex1 is move-constructible? true
Ex1 is trivially move-constructible? false
Ex2 is trivially move-constructible? false

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/is _ trivaly _ move _ constructionable/