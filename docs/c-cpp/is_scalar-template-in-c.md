# 是 C++ 中的 _ 标量模板

> 原文:[https://www.geeksforgeeks.org/is_scalar-template-in-c/](https://www.geeksforgeeks.org/is_scalar-template-in-c/)

C++ STL 的 **std::is_scalar 模板**用于检查给定类型是否为标量类型。它返回一个显示相同内容的布尔值。

**语法**:

```cpp
template < class T > struct is_scalar;
```

**参数**:本模板接受单个参数 **T (Trait 类)**检查 T 是否为标量类型。

**返回值**:该模板返回如下所示的布尔值:

*   **真**:如果类型是标量类型。
*   **False** :如果类型是非标量类型。

下面的程序说明了 C++ STL 中的标准::is _ 标量模板:

**程序 1** :

```cpp
// C++ program to illustrate
// std::is_scalar template

#include <iostream>
#include <type_traits>
using namespace std;

class GFG1 {
};

enum class GFG2 {
    var1,
    var2,
    var3,
    var4
};

// main program
int main()
{

    cout << boolalpha;
    cout << "is_scalar:"
         << endl;
    cout << "GFG1: "
         << is_scalar<GFG1>::value
         << endl;
    cout << "GFG2: "
         << is_scalar<GFG2>::value
         << endl;
    cout << "int[10]: "
         << is_scalar<int[10]>::value
         << endl;
    cout << "int &: "
         << is_scalar<int&>::value
         << endl;
    cout << "char: "
         << is_scalar<char>::value
         << endl;

    return 0;
}
```

**Output:**

```cpp
is_scalar:
GFG1: false
GFG2: true
int[10]: false
int &: false
char: true

```

**程序 2** :

```cpp
// C++ program to illustrate
// std::is_scalar template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    class gfg {
    };

    cout << boolalpha;
    cout << "is_scalar:"
         << endl;
    cout << "int(gfg::*): "
         << is_scalar<int(gfg::*)>::value
         << endl;
    cout << "int *: "
         << is_scalar<int*>::value
         << endl;
    cout << "bool: "
         << is_scalar<bool>::value
         << endl;
    cout << "int(int): "
         << is_scalar<int(int)>::value
         << endl;
    return 0;
}
```

**Output:**

```cpp
is_scalar:
int(gfg::*): true
int *: true
bool: true
int(int): false

```

**程序 3** :

```cpp
// C++ program to illustrate
// std::is_scalar template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
union GFG {
    int var1;
    float var2;
};

int main()
{

    cout << boolalpha;
    cout << "is_scalar:"
         << endl;
    cout << "GFG:"
         << is_scalar<GFG>::value
         << endl;
    cout << "float: "
         << is_scalar<float>::value
         << endl;
    cout << "double: "
         << is_scalar<double>::value
         << endl;
    cout << "char: "
         << is_scalar<char>::value
         << endl;
    cout << "nullptr_t: "
         << is_scalar<std::nullptr_t>::value
         << endl;

    return 0;
}
```

**Output:**

```cpp
is_scalar:
GFG:false
float: true
double: true
char: true
nullptr_t: true

```