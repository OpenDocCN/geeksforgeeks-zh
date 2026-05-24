# std::is_nothrow_move_constructible 在 C++ 中用示例

构造

> 原文: [https://www.geeksforgeeks.org/stdis_nothrow_move_constructible-in-c-with-example/](https://www.geeksforgeeks.org/stdis_nothrow_move_constructible-in-c-with-example/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的 `std::is_nothrow_move_constructible` 模板存在于 `<type_traits>` 头文件中。C++ STL 的 `std::is_nothrow_move_constructible` 模板用于检查给定类型 `T` 是否为 move constructible，这是众所周知的不会抛出任何异常。如果 `T` 是可移动构造类型，则返回布尔值 `true`，否则返回 `false`。

## 头文件

```cpp
#include<type_traits>
```

## 模板类

```cpp
template <class T>
struct is_nothrow_move_constructible;
```

## 语法

```cpp
std::is_nothrow_move_constructible<T>::value
```

## 参数

模板 `std::is_nothrow_move_constructible` 接受单个参数 `T` (Trait 类) 检查 `T` 是否为可移动可构造类型。

## 返回值

此模板返回如下所示的布尔变量:

*   `true`: 如果类型 `T` 是可移动构造类型。
*   `false`: 如果类型 `T` 不是可移动构造类型。

下面是用 C/C++ 说明 `std::is_nothrow_move_constructible` 模板的程序:

## 程序

```cpp
// C++ program to illustrate
// std::is_nothrow_move_constructible
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare structures
struct B {
};

struct A {
    A& operator=(A&) = delete;
};

struct C {
    C(C&&) {}
};

struct D {
    D(D&&) = delete;
};

// Driver Code
int main()
{
    cout << boolalpha;

// Check if int is no throw move
    // constructible or not
    cout << "int: "
         << is_nothrow_move_constructible<int>::value
         << endl;

// Check if char is no throw move
    // constructible or not
    cout << "char: "
         << is_nothrow_move_constructible<char>::value
         << endl;

// Check if floar is no throw move
    // constructible or not
    cout << "float: "
         << is_nothrow_move_constructible<float>::value
         << endl;

// Check if struct A is no throw
    // move constructible or not
    cout << "struct A is nothrow move constructible? "
         << is_nothrow_move_constructible<A>::value
         << endl;

// Check if struct B is no throw
    // move constructible or not
    cout << "struct B is nothrow move constructible? "
         << is_nothrow_move_constructible<B>::value
         << endl;

// Check if struct C is no throw
    // move constructible or not
    cout << "struct C is nothrow move constructible? "
         << is_nothrow_move_constructible<C>::value
         << endl;

// Check if struct D is no throw
    // move constructible or not
    cout << "struct D is nothrow move constructible? "
         << is_nothrow_move_constructible<D>::value
         << endl;

return 0;
}
```

## 输出

```cpp
int: true
char: true
float: true
struct A is nothrow move constructible? true
struct B is nothrow move constructible? true
struct C is nothrow move constructible? false
struct D is nothrow move constructible? false
```

## 参考

[http://www.cplusplus.com/reference/type_traits/is_nothrow_move_constructible/](http://www.cplusplus.com/reference/type_traits/is_nothrow_move_constructible/)