# std::is_trivially_copy_assignable 可赋值 C++ 类，示例

> 原文: [https://www.geeksforgeeks.org/stdis_trivially_copy_assignable-class-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_trivially_copy_assignable-class-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的 `std::is_trivially_copy_assignable` 模板存在于 `<type_traits>` 头文件中。C++ STL 的 `std::is_trivially_copy_assignable` 模板用于检查 `T` 是否是 trivially copy assignable 类型。如果 `T` 是普通复制可赋值类型，则返回布尔值 `true`，否则返回 `false`。

## 头文件:
```cpp
#include<type_traits>
```

## 模板类:
```cpp
template<class T>
struct is_trivially_copy_assignable
```

## 语法:
```cpp
is_trivially_copy_assignable<T>::value
```

## 参数:
模板 `std::is_trivially_copy_assignable` 接受单个参数 `T`（类型特征类），检查 `T` 是否为 trivially copy assignable 类型。

## 返回值:
模板 `std::is_trivially_copy_assignable` 返回如下所示的布尔变量:
*   **真:** 如果类型 `T` 是平凡地复制可赋值的。
*   **假:** 如果类型 `T` 不是平凡地复制可赋值的。

以下是在 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 中演示 `std::is_trivially_copy_assignable` 的程序:

## 程序 1:
```cpp
// C++ program to illustrate
// std::is_trivially_copy_assignable
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare Structures
struct X {
};

struct Y {
    Y& operator=(const Y&)
    {
        return *this;
    }
};

// Driver Code
int main()
{
    cout << std::boolalpha;

    cout << "int? "
         << is_trivially_copy_assignable<int>::value
         << endl;

    cout << "X? "
         << is_trivially_copy_assignable<X>::value
         << endl;

    cout << "Y? "
         << is_trivially_copy_assignable<Y>::value
         << endl;

    cout << "int[2]? "
         << is_trivially_copy_assignable<int[2]>::value
         << endl;
    return 0;
}
```

## 输出:
```cpp
int? true
X? true
Y? false
int[2]? false
```

**参考:** [http://www.cplusplus.com/reference/type_traits/is_trivially_copy_assignable/](http://www.cplusplus.com/reference/type_traits/is_trivially_copy_assignable/)