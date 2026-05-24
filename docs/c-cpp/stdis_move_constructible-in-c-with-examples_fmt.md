# std::is_move_constructible 在 C++ 中的构造示例

> 原文: [https://www.geeksforgeeks.org/stdis_move_constructible-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_move_constructible-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的 `std::is_move_constructible` 模板存在于 `<type_traits>` 头文件中。C++ STL 的 `std::is_move_constructible` 模板用于检查 `T` 是否可移动构造（可以从其类型的右值引用构造）。它返回真或假的布尔值。

## 头文件

```cpp
#include<type_traits>
```

## 模板类

```cpp
template< class T >
struct is_move_constructible;
```

## 语法

```cpp
std::is_move_constructible< datatype >::value << '\n'
```

## 参数

模板 `std::is_move_constructible` 接受单个参数 `T`（Trait 类）检查 `T` 是否为可移动可构造类型。

## 返回值

*   **True:** 如果给定的数据类型 `T` 是 `std::is_move_constructible`。
*   **False:** 如果给定的数据类型 `T` 不是可移动可构造的。

下面是演示 `std::is_move_constructible` 的程序。

## 程序

```cpp
// C++ program to illustrate
// std::is_move_constructible
#include <bits/stdc++.h>
#include <type_traits>

using namespace std;

// Declare structures
struct B {
};
struct A {
    A& operator=(A&) = delete;
};

class C {
    int n;
    C(C&&) = default;
};

class D {
    D(const D&) {}
};

// Driver Code
int main()
{
    cout << boolalpha;

// Check if char is move constructible or not
    cout << "char: "
         << is_move_constructible<char>::value
         << endl;

// Check if struct A is move constructible or not
    cout << "struct A: "
         << is_move_constructible<A>::value
         << endl;

// Check if struct B is move constructible or not
    cout << "struct B: "
         << is_move_constructible<B>::value
         << endl;

// Check if class C is move constructible or not
    cout << "class C: "
         << is_move_constructible<C>::value
         << endl;

// Check if class D is move constructible or not
    cout << "class D: "
         << is_move_constructible<D>::value
         << endl;
    return 0;
}
```

## 输出

```cpp
char: true
struct A: true
struct B: true
class C: false
class D: false
```

**参考:** [http://www.cplusplus.com/reference/type_traits/is_move_constructible/](http://www.cplusplus.com/reference/type_traits/is_move_constructible/)