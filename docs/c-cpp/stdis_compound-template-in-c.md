# STD::is _ c++ 中的复合模板

> 原文:[https://www.geeksforgeeks.org/stdis_compound-template-in-c/](https://www.geeksforgeeks.org/stdis_compound-template-in-c/)

C++ STL 的 **std::is_compound 模板**用于检查类型是否为复合类型。它返回一个显示相同内容的布尔值。

**语法**:

```cpp
template < class T > struct is_compound;

```

**参数**:本模板包含单参数 **T(性状类)**检查 T 是否为复合型。

**返回值**:该模板返回如下所示的布尔值:

*   **真**:如果类型是复合类型。
*   **False** :如果类型是非复合类型。

下面的程序说明了 C++ STL 中的 is_compound 模板:

**程序 1** :

```cpp
// C++ program to illustrate
// is_compound template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
struct GFG1 {
};

union GFG2 {
    int var1;
    float var2;
};

int main()
{
    cout << boolalpha;
    cout << "is_compound:"
         << endl;
    cout << "GFG1: "
         << is_compound<GFG1>::value
         << endl;
    cout << "GFG2: "
         << is_compound<GFG2>::value
         << endl;
    cout << "int: "
         << is_compound<int>::value
         << endl;
    cout << "int*: "
         << is_compound<int*>::value
         << endl;
    return 0;
}
```

**Output:**

```cpp
is_compound:
GFG1: true
GFG2: true
int: false
int*: true

```

**程序 2** :

```cpp
// C++ program to illustrate
// is_compound template

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

// main program
int main()
{
    cout << boolalpha;
    cout << "is_compound:"
         << endl;
    cout << "GFG1: "
         << is_compound<GFG1>::value
         << endl;
    cout << "GFG2: "
         << is_compound<GFG2>::value
         << endl;
    cout << "int[10]: "
         << is_compound<int[10]>::value
         << endl;
    cout << "int &: "
         << is_compound<int&>::value
         << endl;
    cout << "char: "
         << is_compound<char>::value
         << endl;

    return 0;
}
```

**Output:**

```cpp
is_compound:
GFG1: true
GFG2: true
int[10]: true
int &: true
char: false

```

**程序 3** :

```cpp
// C++ program to illustrate
// is_compound template

#include <iostream>
#include <type_traits>
using namespace std;

// driver code
int main()
{
    class gfg {
    };

    cout << boolalpha;
    cout << "is_compound:"
         << endl;
    cout << "int(gfg::*): "
         << is_compound<int(gfg::*)>::value
         << endl;
    cout << "float: "
         << is_compound<float>::value
         << endl;
    cout << "double: "
         << is_compound<double>::value
         << endl;
    cout << "int(int): "
         << is_compound<int(int)>::value
         << endl;

    return 0;
}
```

**Output:**

```cpp
is_compound:
int(gfg::*): true
float: false
double: false
int(int): true

```