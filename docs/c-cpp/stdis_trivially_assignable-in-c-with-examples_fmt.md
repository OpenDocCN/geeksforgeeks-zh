# std::is_trivially_assignable 在 C++ 中的用法与示例

> 原文: [https://www.geeksforgeeks.org/stdis_trivially_assignable-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_trivially_assignable-in-c-with-examples/)

C++ STL 的 `std::is_trivially_assignable` 模板存在于 `<type_traits>` 头文件中。[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的 `std::is_trivially_assignable` 模板用于检查类型 `B` 的值是否可以分配给类型 `A`。它返回真或假的布尔值。

## 头文件

```cpp
#include<type_traits>
```

## 模板类

```cpp
template <class A, class B>
struct is_trivially_assignable;
```

## 语法

```cpp
std::is_trivially_assignable
```

## 参数

*   `A`: 表示要被赋值的对象的类型。
*   `B`: 表示提供值的对象的类型。

## 返回值

模板 `std::is_trivially_assignable` 返回如下所示的布尔变量：

*   **true**: 如果类型 `A` 可以被类型 `B` 赋值。
*   **false**: 如果类型 `A` 不能被类型 `B` 赋值。

以下是在 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 中演示 `std::is_trivially_assignable` 的程序：

## 程序 1

```cpp
// C++ program to illustrate
// std::is_trivially_assignable
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare structures
struct A {
};

struct B {
    B& operator=(const A&) noexcept
    {
        return *this;
    }
    B& operator=(const B&)
    {
        return *this;
    }
};

// Driver Code
int main()
{

cout << boolalpha;

// Check if int& is assignable to
    // double or not
    cout << "is int = double? "
         << is_trivially_assignable<int&,
                                    double>::value
         << endl;

// Check if struct A is assignable to
    // struct A or not
    cout << "is struct A = struct A? "
         << is_trivially_assignable<A, A>::value
         << endl;

return 0;
}
```

## 输出

```cpp
is int = double? true
is struct A = struct A? true
is class B = class A? false
is class B = class B? false
is class AB = class gfg? false
is class Gfg = class gfg? false
```

## 程序 2

```cpp
// C++ program to illustrate
// std::is_trivially_assignable
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare classes
class GfG {
};

class gfg {
};

enum class AB : int { x,
                      y,
                      z };

// Driver Code
int main()
{

cout << boolalpha;

// Check if class GfG is assignable to
    // class gfg or not
    cout << "is class GfG = class gfg? "
         << is_trivially_assignable<GfG, gfg>::value
         << endl;

// Check if class GfG is assignable to
    // class GfG or not
    cout << "is class GfG = class GfG? "
         << is_trivially_assignable<GfG, GfG>::value
         << endl;

// Check if enum class AB is assignable
    // from class gfg or not
    cout << "is class AB = class gfg? "
         << is_trivially_assignable<AB, gfg>::value
         << endl;

// Check if class GfG assignable to
    // class gfg or not
    cout << "is class Gfg = class gfg? "
         << is_trivially_assignable<GfG, gfg>::value
         << endl;
    return 0;
}
```

## 输出

```cpp
is class GfG = class gfg? false
is class GfG = class GfG? true
is class AB = class gfg? false
is class Gfg = class gfg? false
```

**参考:** [http://www.cplusplus.com/reference/type_traits/is_trivially_assignable/](http://www.cplusplus.com/reference/type_traits/is_trivially_assignable/)