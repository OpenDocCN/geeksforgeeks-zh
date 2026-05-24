# STD::is _ enum c++ 中的模板

> 原文:[https://www.geeksforgeeks.org/stdis_enum-template-in-c/](https://www.geeksforgeeks.org/stdis_enum-template-in-c/)

C++ STL 的 **std::is_enum 模板**用于检查给定类型是否为 enum。它返回一个显示相同内容的布尔值。

**语法**:

```cpp
template <class T> struct is_enum;
```

**参数**:本模板接受单参数 **T (Trait 类)**检查 T 是否为枚举类型。

**返回值:**该模板返回如下所示的布尔值:

*   **True:** 如果类型是枚举。
*   **False:** 如果类型是非枚举类型。

下面的程序说明了 C++ 中的标准::is_enum 模板:

**程序 1:** :

```cpp
// C++ program to illustrate
// is_enum template

#include <iostream>
#include <type_traits>
using namespace std;

class GFG1 {
};
enum class GFG2 { var1,
                  var2,
                  var3,
                  var4
};

// Driver code
int main()
{
    cout << boolalpha;
    cout << "is_enum:" << endl;
    cout << "GFG1: "
         << is_enum<GFG1>::value << endl;
    cout << "GFG2: "
         << is_enum<GFG2>::value << endl;

    return 0;
}
```

**Output:**

```cpp
is_enum:
GFG1: false
GFG2: true

```

**程序 2:** :

```cpp
// C++ program to illustrate
// is_enum template

#include <iostream>
#include <type_traits>
using namespace std;

class GFG1 {
};

enum class GFG2 : int {};

// Driver code
int main()
{
    cout << boolalpha;
    cout << "is_enum:" << endl;
    cout << "GFG1: "
         << is_enum<GFG1>::value << '\n';
    cout << "GFG2: "
         << is_enum<GFG2>::value << '\n';
    cout << "int: "
         << is_enum<int>::value << '\n';
    return 0;
}
```

**Output:**

```cpp
is_enum:
GFG1: false
GFG2: true
int: false

```