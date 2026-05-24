# std::is_move_assignable C++ 示例

> 原文: [https://www.geeksforgeeks.org/stdis_move_assignable-c-with-examples/](https://www.geeksforgeeks.org/stdis_move_assignable-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的 `std::is_move_assignable` 模板存在于 `<type_traits>` 头文件中。C++ STL 的 `std::is_move_assignable` 模板用于检查 `T` 是否为移动可赋值类型（可赋同类型的右值引用）。如果 `T` 是移动可赋值类型，则返回布尔值 `true`，否则返回 `false`。

## 头文件

```cpp
#include<type_traits>
```

## 模板类

```cpp
template <class T>
struct is_move_assignable;
```

## 语法

```cpp
std::is_move_assignable<T>::value
```

## 参数

模板 `std::is_move_assignable` 接受单个参数 `T`（类型特征类），检查 `T` 是否为 move assignable。

## 返回值

该模板返回如下所示的布尔变量：

*   `true`：如果类型 `T` 是移动可赋值类型。
*   `false`：如果类型 `T` 不是移动可赋值类型。

下面是用 C/C++ 说明 `std::is_move_assignable` 模板的程序：

## 程序

```cpp
// C++ program to illustrate
// std::is_move_assignable
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare structures
struct A {
};

struct B {
    B& operator=(B&) = delete;
};

struct C {
    ~C() = delete;
};

// Driver Code
int main()
{

    cout << boolalpha;

    // Check if int is move
    // assignable or not
    cout << "int: "
         << is_move_assignable<int>::value
         << endl;

    // Check if struct A is move
    // assignable or not
    cout << "struct A: "
         << is_move_assignable<A>::value
         << endl;

    // Check if struct B is move
    // assignable or not
    cout << "struct B: "
         << is_move_assignable<B>::value
         << endl;

    // Check if struct C is move
    // assignable or not
    cout << "struct C: "
         << is_move_assignable<C>::value
         << endl;

    // Declare an map
    unordered_multimap<int, string> m;
    m.insert({ 1, "GfG" });

    // Check if map m is move
    // assignable or not?
    cout << "Map m: "
         << is_move_assignable<decltype(*m.begin())>::value;

    return 0;
}
```

## 输出

```cpp
int: true
struct A: true
struct B: false
struct C: true
Map m: true
```

## 参考

[http://www.cplusplus.com/reference/type_traits/is_move_assignable/](http://www.cplusplus.com/reference/type_traits/is_move_assignable/)