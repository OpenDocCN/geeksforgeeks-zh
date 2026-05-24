# c++ 中的 type _ traits::is _ null _ pointer

> 原文:[https://www . geesforgeks . org/type _ traitsis _ null _ pointer-in-c/](https://www.geeksforgeeks.org/type_traitsis_null_pointer-in-c/)

C++ STL 的**type _ traits::is _ null_pointer**用于检查给定的类型是否为 null _ pointer。它返回真或假的布尔值。下面是相同的语法:

**头文件:**

```cpp
#include<type_traits>

```

**语法:**

```cpp
template class T struct is_null_pointer;

```

**参数:**模板**type _ traits::is _ null_pointer**接受单个参数 T (Trait 类)检查 T 是否为 null _ pointer。

**返回值:**

*   **True** : If the type is null pointer.
*   **False** : If the pointer is not an empty pointer.

下面的程序说明了 C++ STL 中的**标准::is_null_pointer** 模板:

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

**程序二:**

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

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/is _ null _ pointer/