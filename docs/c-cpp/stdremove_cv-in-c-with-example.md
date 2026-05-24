# 标准::移除 C++ 中的 _cv，示例

> 原文:[https://www . geesforgeks . org/stdremove _ cv-in-c-with-example/](https://www.geeksforgeeks.org/stdremove_cv-in-c-with-example/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的 **std::remove_cv** 模板存在于< type_traits >头文件中。C++ STL 的 **std::remove_cv** 模板用于获取没有 **const** 和 **volatile** 资质的 **T** 类型。如果 **T** 没有常量和变量限定，则返回布尔值 true，否则返回 false。

**头文件:**

```cpp
#include<type_traits>

```

**模板:**

```cpp
template<class T>
struct remove_cv;

```

**语法:**

```cpp
std::remove_cv<T>::type a;

```

**参数:**模板 **std::remove_cv** 接受单个参数 **T(性状类)**检查 **T** 是否无常量，挥发合格。

**返回值:**

下面是用 C++ 演示 **std::remove_cv** 的程序:

**程序:**

```cpp
// C++ program to illustrate std::remove_cv
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Driver Code
int main()
{

    // Declare variable of type int, const
    // int, volatile int and const volatile int
    typedef remove_cv<int>::type A;
    typedef remove_cv<const int>::type B;
    typedef remove_cv<volatile int>::type C;
    typedef remove_cv<const volatile int&>::type D;

    cout << boolalpha;

    cout << "A: "
         << is_same<const volatile int, A>::value
         << endl;

    cout << "B: "
         << is_same<const volatile int, B>::value
         << endl;

    cout << "C: "
         << is_same<int, C>::value
         << endl;

    cout << "D: "
         << is_same<int, D>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
A: false
B: false
C: true
D: false

```

**参考:**T2】http://www.cplusplus.com/reference/type_traits/remove_cv/