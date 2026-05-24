# 是 C++ 中的 _class 模板

> 原文:[https://www . geesforgeks . org/is _ class-in-CPP-with-examples/](https://www.geeksforgeeks.org/is_class-in-cpp-with-examples/)

C++ STL 的 **std::is_class 模板**用于检查给定类型是否为类。它返回一个显示相同内容的布尔值。

**语法:**

```cpp
template <class T> struct is_class;

```

**参数:**本模板接受单参数 **T(性状类)**检查 T 是否为类。

**返回值**:该模板返回如下所示的布尔值:

*   **True:** 如果类型是类类。
*   **False:** 如果类型是类类。

下面的程序说明了 C++ 中的 std::is_class 模板:

**程序 1:** :

```cpp
// C++ program to illustrate
// is_class template

#include <iostream>
#include <type_traits>
using namespace std;

class GFG1 {
};

union GFG2 {
    int var1;
    float var2;
};

int main()
{
    cout << boolalpha;
    cout << "is_class:" << endl;
    cout << "GFG1: "
         << is_class<GFG1>::value << endl;
    cout << "GFG2: "
         << is_class<GFG2>::value << endl;
    return 0;
}
```

**Output:**

```cpp
is_class:
GFG1: true
GFG2: false

```

**程序 2** :

```cpp
// C++ program to illustrate
// is_class template

#include <iostream>
#include <type_traits>
using namespace std;

class GFG1 {
    int var1;
    float var2;
    char var3;
};

struct GFG2 {
    union {
        int var4;
        float var5;
    };
};

int main()
{
    cout << boolalpha;
    cout << "is_class:" << endl;
    cout << "int: "
         << is_class<int>::value << endl;
    cout << "GFG1: "
         << is_class<GFG1>::value << endl;
    cout << "GFG2: "
         << is_class<GFG2>::value << endl;
    return 0;
}
```

**Output:**

```cpp
is_class:
int: false
GFG1: true
GFG2: true

```