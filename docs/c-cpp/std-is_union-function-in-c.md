# std 是 C++ 中的 _union()模板

> 原文:[https://www.geeksforgeeks.org/std-is_union-function-in-c/](https://www.geeksforgeeks.org/std-is_union-function-in-c/)

C++ STL 的 **std::is_union 模板**用于检查给定类型是否为 union。它返回一个显示相同内容的布尔值。

**语法**:

```cpp
template <class T> struct is_union;
```

**参数:**本模板接受单参数 **T(性状类)**检查 T 是否为并集。

**返回值**:该模板返回如下所示的布尔值:

*   **True:** 如果类型是联合类。
*   **False:** 如果类型是非并集类。

下面的程序说明了 C++ 中的标准::is_union 模板:

**程序 1:** :

```cpp
// C++ program to illustrate
// is_union template

#include <iostream>
#include <type_traits>
using namespace std;

struct GFG1 {
};

union GFG2 {
    int var1;
    float var2;
};

int main()
{
    cout << boolalpha;
    cout << "is_union:" << endl;
    cout << "GFG1: "
         << is_union<GFG1>::value << endl;
    cout << "GFG2: "
         << is_union<GFG2>::value << endl;
    return 0;
}
```

**Output:**

```cpp
is_union:
GFG1: false
GFG2: true

```

**程序 2** :

```cpp
// C++ program to illustrate
// is_union template

#include <iostream>
#include <type_traits>
using namespace std;

union GFG1 {
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
    cout << "is_union:" << endl;
    cout << "int: "
         << is_union<int>::value << endl;
    cout << "GFG1: "
         << is_union<GFG1>::value << endl;
    cout << "GFG2: "
         << is_union<GFG2>::value << endl;
    return 0;
}
```

**Output:**

```cpp
is_union:
int: false
GFG1: true
GFG2: false

```