# std::is_trivially_constructible 在 C++ 中的使用示例

## 进行简单的构造

> 原文: [https://www.geeksforgeeks.org/stdis_trivially_constructible-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_trivially_constructible-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的 `std::is_trivially_constructible` 模板存在于 `<type_traits>` 头文件中。C++ STL 的 `std::is_trivially_constructible` 模板用于检查给定的类型 `T` 是否是带有参数集的平凡可构造类型。如果 `T` 是平凡可构造类型，它返回布尔值 `true`，否则返回 `false`。

### 头文件

```cpp
#include<type_traits>
```

### 模板类

```cpp
template <class T, class... Args>
struct is_trivially_constructible;
```

### 语法

```cpp
std::is_trivially_constructible<T, Args...>::value
```

### 参数

模板 `std::is_trivially_constructible` 接受两个参数：

*   `T`: 一个数据类型或具有未知绑定的数组。
*   `Args...`: 一个数据类型列表，表示构造函数形式的参数类型，顺序与构造函数相同。

### 返回值

这个模板返回一个如下所示的布尔变量：

*   `true`: 如果类型 `T` 是平凡可构造类型。
*   `false`: 如果类型 `T` 不是平凡可构造类型。

下面是用 C++ 说明 `std::is_trivially_constructible` 的程序：

### 程序 1

```cpp
// C++ program to illustrate
// std::is_trivially_constructible
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare structures
struct Ex1 {
    std::string str;
};
struct Ex2 {
    int n;
    Ex2() = default;
};

struct A {
    // Constructor
    A(int, int){};
};

// Driver Code
int main()
{
    cout << boolalpha;

    // Check if Ex1 is a trivally
    // constructible or not
    cout << "Ex1: "
         << is_trivially_constructible<Ex1>::value
         << endl;

    // Check if struct Ex2 is a trivally
    // constructible or not
    cout << "Ex2: "
         << is_trivially_constructible<Ex2>::value
         << endl;

    // Check if A(int, float) is a trivally
    // constructible or not
    cout << "A(int, int): "
         << is_trivially_constructible<A(int, int)>::value
         << endl;
    return 0;
}
```

### 输出

```cpp
Ex1: false
Ex2: true
A(int, int): false
```

### 程序 2

```cpp
// C++ program to illustrate
// std::is_trivially_constructible
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare structures
struct X {
};

struct Y {
    // Default Constructor
    Y() {}

    // Parameterized Constructor
    Y(const X&) noexcept {}
};

// Driver Code
int main()
{
    cout << boolalpha;

    // Check if int is a trivally
    // constructible or not
    cout << "int(): "
         << is_trivially_constructible<int>::value
         << endl;

    // Check if struct Y is a trivally
    // constructible or not
    cout << "Y(): "
         << is_trivially_constructible<Y>::value
         << endl;

    // Check if Y(X) is a trivally
    // constructible or not
    cout << "Y(X): "
         << is_trivially_constructible<Y, X>::value
         << endl;

    return 0;
}
```

### 输出

```cpp
int(): true
Y(): false
Y(X): false
```

参考: [http://www.cplusplus.com/reference/type_traits/is_trivially_constructible/](http://www.cplusplus.com/reference/type_traits/is_trivially_constructible/)