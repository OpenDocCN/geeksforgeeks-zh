# STD::is _ c++ 中的函数模板，带示例

> 原文:[https://www . geesforgeks . org/stdis _ function-template-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_function-template-in-c-with-examples/)

C++ STL 的 **std::is_function** 用来检查给定的 T 类型是否是函数。它返回真或假的布尔值。下面是相同的语法:

**头文件:**

```cpp
#include<type_traits>

```

**语法:**

```cpp
template 
  <class T> 
  struct is_function;

```

**参数:**模板 **std::is_function** 接受单个参数 T (Trait 类)检查 T 是否为函数。

**返回值:**

*   True: if t is a function type.
*   False: If t is not a function type.

以下程序说明了 C++ STL 中的 **std::is_function** 模板:

**程序 1:**

```cpp
// C++ program to illustrate
// is_function template

#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

struct GeeksforGeeks {
    int func() const&;
};

template <typename>
struct Computer {
};

template <class A, class B>
struct Computer<B A::*> {
    using member_type = B;
};

int GFG();

int main()
{
    cout << boolalpha;
    cout << is_function<GeeksforGeeks>::value
         << endl;
    cout << is_function<int(int)>::value
         << endl;
    cout << is_function<decltype(GFG)>::value
         << endl;
    cout << is_function<int>::value
         << endl;

    using A = Computer<decltype(
        &GeeksforGeeks::func)>::member_type;
    cout << is_function<A>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
false
true
true
false
true

```

**程序二:**

```cpp
// C++ program to illustrate
// is_function template

#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

struct GeeksforGeeks {
    int func() const&;
};

template <typename>
struct Computer {
};

template <class A, class B>
struct Computer<B A::*> {
    using member_type = B;
};

int GFG();

int main()
{
    cout << boolalpha;
    cout << is_function<int(int)>::value
         << endl;
    cout << is_function<GeeksforGeeks>::value
         << endl;
    cout << is_function<int>::value
         << endl;
    cout << is_function<decltype(GFG)>::value
         << endl;

    using A = Computer<decltype(
        &GeeksforGeeks::func)>::member_type;
    cout << is_function<A>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
true
false
false
true
true

```

**参考:**T2】http://www.cplusplus.com/reference/type_traits/is_function/