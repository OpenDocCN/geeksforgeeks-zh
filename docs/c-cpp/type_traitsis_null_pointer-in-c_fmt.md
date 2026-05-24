# C++ 中的 `type_traits::is_null_pointer`

> 原文: [https://www.geeksforgeeks.org/type_traitsis_null_pointer-in-c/](https://www.geeksforgeeks.org/type_traitsis_null_pointer-in-c/)

C++ STL 的 `type_traits::is_null_pointer` 用于检查给定的类型是否为 `nullptr`。它返回真或假的布尔值。下面是相同的语法：

**头文件:**

```cpp
#include<type_traits>
```

**语法:**

```cpp
template<class T> struct is_null_pointer;
```

**参数:** 模板 `type_traits::is_null_pointer` 接受单个参数 `T` (Trait 类) 检查 `T` 是否为 `nullptr`。

**返回值:**

*   **True**: 如果类型是空指针。
*   **False**: 如果指针不是空指针。

下面的程序说明了 C++ STL 中的 `std::is_null_pointer` 模板：

**程序 1:**

```cpp
// C++ program to illustrate
// is_null_pointer template

#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Driver Code
int main()
{

    cout << boolalpha;
    cout << "is_null_pointer:" << endl;
    cout << "int *&: "
         << is_null_pointer<decltype(nullptr)>::value
         << '\n';
    cout << "int *[10]: "
         << is_null_pointer<int * [10]>::value
         << '\n';
    cout << "float *: "
         << is_null_pointer<float*>::value
         << '\n';
    cout << "int[10]:"
         << is_null_pointer<int[10]>::value
         << '\n';

    return 0;
}
```

**输出:**

```cpp
is_null_pointer:
int *&: true
int *[10]: false
float *: false
int[10]:false
```

**程序 2:**

```cpp
// C++ program to illustrate
// is_null_pointer template

#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Driver Code
int main()
{

    cout << boolalpha
         << is_null_pointer<decltype(nullptr)>::value
         << endl
         << is_null_pointer<int*>::value
         << endl
         << is_pointer<decltype(nullptr)>::value
         << endl
         << is_pointer<int*>::value
         << endl;
}
```

**输出:**

```cpp
true
false
false
true
```

**参考:** [http://www.cplusplus.com/reference/type_traits/is_null_pointer/](http://www.cplusplus.com/reference/type_traits/is_null_pointer/)