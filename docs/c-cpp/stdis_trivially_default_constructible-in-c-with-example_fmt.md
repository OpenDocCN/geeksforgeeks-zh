# std::is_trivially_default_constructible in C++ with Example

> 原文: [https://www.geeksforgeeks.org/stdis_trivially_default_constructible-in-c-with-example/](https://www.geeksforgeeks.org/stdis_trivially_default_constructible-in-c-with-example/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的 `std::is_trivially_default_constructible` 模板存在于 `<type_traits>` 头文件中。C++ STL 的 `std::is_trivially_default_constructible` 模板用于检查 `T` 是否是 trivially default constructible 类型。如果 `T` 是平凡默认可构造类型，则返回布尔值 true，否则返回 false。

## Header

```cpp
#include<type_traits>
```

## Template Class

```cpp
template< class T >
struct is_trivially_default_constructible;
```

## Syntax

```cpp
std::is_trivially_default_constructible<T>::value
```

## Parameters

模板 `std::is_trivially_default_constructible` 接受单个参数 `T` (Trait 类) 检查 `T` 是否为 trivially default constructible 类型。

## Return Value

模板 `std::is_trivially_default_constructible` 返回如下所示的布尔变量:

*   **True:** 如果类型 `T` 是平凡默认可构造的。
*   **False:** 如果类型 `T` 不是平凡默认可构造的。

下面是用 C++ 演示 `std::is_trivially_default_constructible` 的程序:

### Program 1

```cpp
// C++ program to demonstrate
// std::is_trivially_default_constructible
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
    // default constructible or not
    cout << "int: "
         << is_trivially_default_constructible<int>::value
         << endl;

// Check if class A is trivially
    // default constructible or not
    cout << "class A: "
         << is_trivially_default_constructible<A>::value
         << endl;

// Check if class B is trivially
    // default constructible or not
    cout << "class B: "
         << is_trivially_default_constructible<B>::value
         << endl;

// Check if enum class C is trivially
    // default constructible or not
    cout << "enum class C: "
         << is_trivially_default_constructible<C>::value
         << endl;

// Check if class D is trivially
    // default constructible or not
    std::cout << "class D: "
              << is_trivially_default_constructible<D>::value
              << endl;
    return 0;
}
```

### Output

```cpp
int: true
class A: true
class B: false
enum class C: true
class D: false
```

### Program 2

```cpp
// C++ program to demonstrate
// std::is_trivially_default_constructible
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

// Check if struct Ex1 is default
    // constructible or not
    cout << "Ex1 is default-constructible? "
         << is_trivially_default_constructible<Ex1>::value
         << '\n';

// Check if struct Ex1 is trivially
    // defaultconstructible or not
    cout << "Ex1 is trivially default-constructible? "
         << is_trivially_default_constructible<Ex1>::value
         << '\n';

// Check if struct Ex2 is trivially
    // defaultconstructible or not
    cout << "Ex2 is trivially default-constructible? "
         << is_trivially_default_constructible<Ex2>::value
         << '\n';
}
```

### Output

```cpp
Ex1 is default-constructible? false
Ex1 is trivially default-constructible? false
Ex2 is trivially default-constructible? false
```

**参考:** [http://www.cplusplus.com/reference/type_traits/is_trivially_default_constructible/](http://www.cplusplus.com/reference/type_traits/is_trivially_default_constructible/)