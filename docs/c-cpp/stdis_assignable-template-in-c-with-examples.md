# STD::is _ 可赋值模板 C++ 示例

> 原文:[https://www . geesforgeks . org/stdis _ assigned-template-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_assignable-template-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的**STD::is _ assigned**模板存在于**<**type _ traits**>**头文件中。C++ STL 的**STD::is _ assigned**模板用于检查 B 类型的值是否可以赋给 a，返回真或假的布尔值。下面是相同的语法:

**头文件:**

```cpp
#include<type_traits>

```

**语法:**

```cpp
template 
  <class A, class B> 
  struct is_assignable;;

```

**参数:**接受以下参数:

*   **A** :表示接受赋值的对象类型。
*   **B** :表示提供值的对象类型。

**返回值:**模板**标准::is_assignable():** 返回一个布尔值，即真或假。

以下是演示**STD::is _ assigned():**的程序

**程序 1:**

```cpp
// C++ program to illustrate
// is_assignable example

#include <bits/stdc++.h>
#include <type_traits>

using namespace std;

struct A {
};
struct B {
    B& operator=(const A&)
    {
        return *this;
    }
};

// Driver Code
int main()
{
    cout << boolalpha;
    cout << "is_assignable:" << endl;
    cout << "A = B: "
         << is_assignable<A, B>::value
         << endl;
    cout << "B = A: "
         << is_assignable<B, A>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
is_assignable:
A = B: false
B = A: true

```

**程序二:**

```cpp
// C++ program to illustrate
// is_assignable example

#include <bits/stdc++.h>

#include <type_traits>

using namespace std;

struct B {
};
struct A {
    A& operator=(const B&)
    {
        return *this;
    }
};

// Driver Code
int main()
{
    cout << boolalpha;
    cout << "is_assignable:" << endl;
    cout << "A = B: "
         << is_assignable<A, B>::value
         << endl;
    cout << "B = A: "
         << is_assignable<B, A>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
is_assignable:
A = B: true
B = A: false

```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/is _ assigned/