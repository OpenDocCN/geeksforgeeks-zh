# STD::c++ 中 has_virtual_destructor 示例

> 原文:[https://www . geesforgeks . org/stdhas _ virtual _ destructor-in-c-with-examples/](https://www.geeksforgeeks.org/stdhas_virtual_destructor-in-c-with-examples/)

C++ STL 的**STD::has _ virtual _ destructor**用于检查给定的类型 T 是否有虚拟析构函数。它返回真或假的布尔值。以下是相同的语法:
**头文件:**

```cpp
#include<type_traits>
```

**语法:**

```cpp
template
  <class T>
  struct has_virtual_destructor;
```

**参数:**模板**STD::has _ virtual _ destructor**接受单个参数 T (Trait 类)来检查 T 是否有虚析构函数。
**返回值:**

*   如果存在虚拟析构函数，则为真。
*   False:如果虚拟析构函数不存在。

下面的程序说明了 C++ STL 中的**STD::has _ virtual _ destructor**模板:
T3】程序 1:T5】

## CPP14

```cpp
// C++ program to illustrate
// has_virtual_destructor example

#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

struct gfg1 {
};
struct gfg2 {
    virtual ~gfg2() {}
};
struct gfg3 : gfg2 {
};

// Driver Code
int main()
{
    cout << boolalpha;
    cout << "has_virtual_destructor:"
         << endl;
    cout << "int: "
         << has_virtual_destructor<int>::value
         << endl;
    cout << "gfg1: "
         << has_virtual_destructor<gfg1>::value
         << endl;
    cout << "gfg2: "
         << has_virtual_destructor<gfg2>::value
         << endl;
    cout << "gfg3: "
         << has_virtual_destructor<gfg3>::value
         << endl;

    return 0;
}
```

**Output:** 

```cpp
has_virtual_destructor:
int: false
gfg1: false
gfg2: true
gfg3: true
```

**节目 2:**

## CPP14

```cpp
// C++ program to illustrate
// has_virtual_destructor example

#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

struct gfg1 {
    virtual ~gfg1() {}
};
struct gfg2 {
};
struct gfg3 : gfg1 {
};

// Driver Code
int main()
{
    cout << boolalpha;
    cout << "has_virtual_destructor:"
         << endl;
    cout << "int: "
         << has_virtual_destructor<int>::value
         << endl;
    cout << "gfg1: "
         << has_virtual_destructor<gfg1>::value
         << endl;
    cout << "gfg2: "
         << has_virtual_destructor<gfg2>::value
         << endl;
    cout << "gfg3: "
         << has_virtual_destructor<gfg3>::value
         << endl;

    return 0;
}
```

**Output:** 

```cpp
has_virtual_destructor:
int: false
gfg1: true
gfg2: false
gfg3: true
```

**参考:**T2【http://www . cplusplus . com/Reference/type _ traits/has _ virtual _ destructor/T4】