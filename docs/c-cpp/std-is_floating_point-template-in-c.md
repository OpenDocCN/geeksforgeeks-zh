# 标准是 C++ 中的 _ 浮点模板

> 原文:[https://www . geesforgeks . org/STD-is _ floating _ point-template-in-c/](https://www.geeksforgeeks.org/std-is_floating_point-template-in-c/)

C++ STL 的 **std::is_floating_point 模板**用于检查给定类型是否为浮点值。它返回一个显示相同内容的布尔值。

**语法:**

```cpp
template < class T > struct is_floating_point;
```

**参数:**该模板接受单个参数 **T (Trait 类)**检查 T 是否为浮点类型。

**返回值:**该模板返回如下所示的布尔值:

*   **True:** 如果类型是浮点型。
*   **False:** 如果类型为非浮点值。

下面的程序说明了 C++ STL 中的标准::is _ 浮点模板:

**程序 1:**

```cpp
// C++ program to illustrate
// std::is_floating_point template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    cout << std::boolalpha;
    cout << "is_floating_point:" << endl;
    cout << "char: "
         << is_floating_point<char>::value
         << endl;
    cout << "int: "
         << is_floating_point<int>::value
         << endl;
    cout << "float: "
         << is_floating_point<float>::value
         << endl;
    return 0;
}
```

**Output:**

```cpp
is_floating_point:
char: false
int: false
float: true

```

**程序 2:**

```cpp
// C++ program to illustrate
// std::is_floating_point template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    cout << std::boolalpha;
    cout << "is_floating_point:" << endl;
    cout << "double: "
         << is_floating_point<double>::value
         << endl;
    cout << "bool: "
         << is_floating_point<bool>::value
         << endl;
    cout << "long int: "
         << is_floating_point<long int>::value
         << endl;
    return 0;
}
```

**Output:**

```cpp
is_floating_point:
double: true
bool: false
long int: false

```

**程序 3:**

```cpp
// C++ program to illustrate
// std::is_floating_point function
#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    cout << boolalpha;
    cout << "is_floating_point:" << endl;
    cout << "wchar_t: "
         << is_floating_point<wchar_t>::value
         << endl;
    cout << "long double: "
         << is_floating_point<long double>::value
         << endl;
    cout << "unsigned short int: "
         << is_floating_point<unsigned short int>::value
         << endl;

    return 0;
}
```

**Output:**

```cpp
is_floating_point:
wchar_t: false
long double: true
unsigned short int: false

```