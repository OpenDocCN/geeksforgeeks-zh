# STD::is _ c++ 中的整型模板

> 原文:[https://www.geeksforgeeks.org/stdis_integral-in-c/](https://www.geeksforgeeks.org/stdis_integral-in-c/)

C++ STL 的 **std::is_integral 模板**用于检查给定类型是否为整数。它返回一个显示相同内容的布尔值。

**语法:**

```cpp
template <class T> struct is_integral;
```

**模板参数**:该模板接受单个参数 **T(性状类)**检查 T 是否为整型。

**返回值**:该模板返回如下所示的布尔值:

*   **真**:如果类型是积分。
*   **假**:如果类型是非整数。

下面的程序说明了 C++ 中的标准::is_integral 模板:

**程序 1:** :

```cpp
// C++ program to illustrate
// is_integral function

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    cout << boolalpha;
    cout << "is_integral:" << endl;
    cout << "char: " << is_integral
       <char>::value << endl;
    cout << "int: " << is_integral
       <int>::value << endl;
    cout << "float: " << is_integral
        <float>::value << endl;
    return 0;
}
```

**Output:**

```cpp
is_integral:
char: true
int: true
float: false

```

**程序 2:** :

```cpp
// C++ program to illustrate
// is_integral function

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    cout << boolalpha;
    cout << "is_integral:" << endl;
    cout << "double: " << is_integral
      <double>::value << endl;
    cout << "bool: " << is_integral
       <bool>::value << endl;
    cout << "long int: " << is_integral
        <long int>::value << endl;
    return 0;
}
```

**Output:**

```cpp
is_integral:
double: false
bool: true
long int: true

```

**程序 3:** :

```cpp
// C++ program to illustrate
// is_integral function

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    cout << boolalpha;
    cout << "is_integral:" << endl;
    cout << "wchar_t: " << is_integral
      <wchar_t>::value << endl;
    cout << "long double: " << is_integral
      <long double>::value << endl;
    cout << "unsigned short int: " << is_integral
      <unsigned short int>::value << endl;
    return 0;
}
```

**Output:**

```cpp
is_integral:
wchar_t: true
long double: false
unsigned short int: true

```