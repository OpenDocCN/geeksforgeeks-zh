# 标准::C++ 中的 remove_const 示例

> 原文:[https://www . geesforgeks . org/stdremove _ const-in-c-with-examples/](https://www.geeksforgeeks.org/stdremove_const-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的 **std::remove_const** 模板存在于**T12】type _ traits>T5】头文件中。C++ STL 的 **std::remove_const** 模板用于获取没有 const 限定的类型 **T** 。如果 **T** 没有常量限定，则返回布尔值 true，否则返回 false。下面是相同的语法:**

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template <class T>
struct remove_const;

```

**语法:**

```cpp
std::remove_const<T>::value

```

**参数:**此模板 **std::remove_const** 接受单个参数 **T(性状类)**检查 **T** 是否无 const 合格。

**返回值:**模板 **std::remove_const** 返回布尔值:

*   **true:** If the type **t** is not qualified by const.
*   **False:** If the type **t** is const qualified.

以下是在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中演示 **std::remove_const** 的程序:

**程序:**

```cpp
// C++ program to illustrate
// std::remove_const
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Driver Code
int main()
{
    // Declare variable of type
    // int, const int, const int*,
    // int * const and const int&
    typedef remove_const<int>::type A;
    typedef remove_const<const int>::type B;
    typedef remove_const<const int*>::type C;
    typedef remove_const<int* const>::type D;
    typedef remove_const<const int&>::type E;

    cout << std::boolalpha;

    // Checking const of the above
    // declared variables
    cout << "A is without const int? "
         << is_same<int, A>::value
         << endl;

    cout << "B is without const int? "
         << is_same<int, B>::value
         << endl;

    cout << "C is without const int? "
         << is_same<int, C>::value
         << endl;

    cout << "D is without const int? "
         << is_same<int, D>::value
         << endl;

    cout << "E is without const int? "
         << is_same<const int, E>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
A is without const int? true
B is without const int? true
C is without const int? false
D is without const int? false
E is without const int? false

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/remove _ const/