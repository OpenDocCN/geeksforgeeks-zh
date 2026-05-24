# std::is_nothrow_copy_constructible 可在 C++ 中构造，示例

> 原文: [https://www.geeksforgeeks.org/stdis_nothrow_copy_constructible-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_nothrow_copy_constructible-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的 `std::is_nothrow_copy_constructible` 模板存在于 `<type_traits>` 头文件中。C++ STL 的 `std::is_nothrow_copy_constructible` 模板用于检查 `T` 是否为可复制构造类型，这是众所周知的不抛出任何异常。如果 `T` 是可复制构造类型，则返回布尔值 `true`，否则返回 `false`。

## 头文件

```cpp
#include<type_traits>
```

## 模板类

```cpp
template <class T>
struct is_nothrow_copy_constructible
```

## 语法

```cpp
is_nothrow_copy_constructible<T>::value
```

## 参数

模板 `std::is_nothrow_copy_constructible` 接受单个参数 `T` (Trait 类) 检查 `T` 是否为可复制构造类型。

## 返回值

模板 `std::is_nothrow_copy_constructible` 返回如下所示的布尔变量:

*   `true`: 如果类型 `T` 是可复制构造类型。
*   `false`: 如果类型 `T` 不是可复制构造类型。

下面是在 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 中演示 `std::is_nothrow_copy_constructible` 的程序:

## 程序 1

```cpp
// C++ program to illustrate
// std::is_nothrow_copy_constructible
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Define Classes
class X {
};

class Y {
    Y(const Y&) {}
};

// Driver Code
int main()
{

    cout << boolalpha;

    // Check if int is no throw copy
    // constructible
    cout << "int: "
         << is_nothrow_copy_constructible<int>::value
         << endl;

    // Check if class X is no throw copy
    // constructible
    cout << "class X: "
         << is_nothrow_copy_constructible<X>::value
         << endl;

    // Check if class Y is no throw copy
    // constructible
    cout << "class Y: "
         << is_nothrow_copy_constructible<Y>::value
         << endl;

    return 0;
}
```

## 输出

```cpp
int: true
class X: true
class Y: false
```

## 程序 2

```cpp
// C++ program to illustrate
// std::is_nothrow_copy_constructible
#include <iostream>
#include <type_traits>
using namespace std;

// Declare structures
struct A {
};

struct B {
    B(const B&) {}
};

struct C {
    C(const C&)
    noexcept {}
};

// Driver Code
int main()
{

    cout << boolalpha;
    cout << "is_nothrow_copy_constructible:"
         << endl;

    cout << "int is_nothrow_copy_constructible? "
         << is_nothrow_copy_constructible<int>::value
         << endl;

    cout << "A is_nothrow_copy_constructible? "
         << is_nothrow_copy_constructible<A>::value
         << endl;

    cout << "B is_nothrow_copy_constructible? "
         << is_nothrow_copy_constructible<B>::value
         << endl;

    cout << "C is_nothrow_copy_constructible? "
         << is_nothrow_copy_constructible<C>::value
         << endl;

    return 0;
}
```

## 输出

```cpp
is_nothrow_copy_constructible:
int is_nothrow_copy_constructible? true
A is_nothrow_copy_constructible? true
B is_nothrow_copy_constructible? false
C is_nothrow_copy_constructible? true
```

**参考:** [http://www.cplusplus.com/reference/type_traits/is_nothrow_copy_constructible/](http://www.cplusplus.com/reference/type_traits/is_nothrow_copy_constructible/)