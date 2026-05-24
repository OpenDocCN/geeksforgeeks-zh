# std::is_nothrow_constructible可在C++中用示例构造

> 原文: [https://www.geeksforgeeks.org/stdis_nothrow_constructible-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_nothrow_constructible-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的`std::is_nothrow_constructible`模板存在于`<type_traits>`头文件中。C++ STL 的`std::is_nothrow_constructible`模板用于检查给定的类型 `T` 是否是带参数集的可构造类型，这是众所周知的不抛出任何异常。如果 `T` 是可构造类型，它返回布尔值 `true`，否则返回 `false`。

## 头文件:

```cpp
#include<type_traits>
```

## 模板类:

```cpp
template< class T, class... Args >
struct is_nothrow_constructible;
```

## 语法:

```cpp
std::is_nothrow_constructible<T, Args..>::value
```

## 参数:

模板`std::is_nothrow_constructible`接受以下参数:

*   `T`: It represents a data type.
*   `Args`: indicates the data type list `T`.

## 返回值:

模板`std::is_nothrow_constructible`返回如下所示的布尔变量:

*   `true`: If the type `T` can be constructed from `Args` without throwing any exceptions.
*   `false`: If the type `T` cannot be constructed from `Args`.

下面是用 C++ 演示`std::is_nothrow_constructible`的程序:

## 程序1:

```cpp
// C++ program to illustrate
// std::is_nothrow_constructible
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare structures
struct X {
};

struct Y {
    Y() {}
    Y(X&) noexcept {}
};

struct Z {
    int n;
    Z() = default;
};

// Driver Code
int main()
{
    cout << boolalpha;

    cout << "int is_nothrow_constructible? "
         << is_nothrow_constructible<int>::value
         << endl;

    cout << "X() is is_nothrow_constructible? "
         << is_nothrow_constructible<X>::value
         << endl;

    cout << "Y(X) is is_nothrow_constructible? "
         << is_nothrow_constructible<Y, X>::value
         << endl;

    cout << "Z() is is_nothrow_constructible? "
         << is_nothrow_constructible<Z>::value
         << endl;
    return 0;
}
```

## 输出:

```cpp
int is_nothrow_constructible? true
X() is is_nothrow_constructible? true
Y(X) is is_nothrow_constructible? false
Z() is is_nothrow_constructible? true
```

## 程序2:

```cpp
// C++ program to illustrate
// std::is_nothrow_constructible
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Class GfG
class GfG {
    int v1;
    float v2;

public:
    GfG(int n)
        : v1(n), v2()
    {
    }
    GfG(int n, double f) noexcept : v1(n), v2(f) {}
};

// Declare Structure
struct X {
    int n;
    X() = default;
};

// Driver Code
int main()
{
    cout << boolalpha;

    cout << "GfG is Nothrow-constructible from int? "
         << is_nothrow_constructible<GfG, int>::value
         << '\n';

    cout << "GfG is Nothrow-constructible from int and float? "
         << is_nothrow_constructible<GfG, int, float>::value
         << '\n';

    cout << "GfG is Nothrow-constructible from struct X? "
         << is_nothrow_constructible<GfG, X>::value
         << '\n';
}
```

## 输出:

```cpp
GfG is Nothrow-constructible from int? false
GfG is Nothrow-constructible from int and float? true
GfG is Nothrow-constructible from struct X? false
```

**参考:** [http://www.cplusplus.com/reference/type_traits/is_nothrow_constructible/](http://www.cplusplus.com/reference/type_traits/is_nothrow_constructible/)