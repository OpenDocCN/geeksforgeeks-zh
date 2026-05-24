# C++
## std::numeric_limits::max() 和 std::numeric_limits::min()

> 原文: [https://www.geeksforgeeks.org/stdnumeric_limitsmax-and-stdnumeric_limitsmin-in-c/](https://www.geeksforgeeks.org/stdnumeric_limitsmax-and-stdnumeric_limitsmin-in-c/)

### std::numeric_limits::max()

`std::numeric_limits<T>::max()` 函数用于获取数值类型 `T` 所能表示的最大有限值。所有算术类型对类型 `T` 有效。

**头文件:**
```cpp
#include<limits>
```

**模板:**
```cpp
static T max() throw();
static constexpr T max() noexcept;
```

**语法:**
```cpp
std::numeric_limits<T>::max
```

**参数:** 接收任意一种数据类型，即 `T`。

**返回类型:** 返回预定义的[宏](https://www.geeksforgeeks.org/data-type-ranges-and-their-macros-in-c/)，`true` 或 `default T()` 取决于类型 `T`。一些标准返回值为:

| Type `t` | `std::numeric_limits<t>::max()` |
| --- | --- |
| `bool` | `true` |
| `char` | `CHAR_MAX` |
| `signed char` | `SCHAR_MAX` |
| `unsigned char` | `UCHAR_MAX` |
| `wchar_t` | `WCHAR_MAX` |
| `short` | `SHRT_MAX` |
| `int` | `INT_MAX` |
| `unsigned int` | `UINT_MAX` |
| `long` | `LONG_MAX` |
| `unsigned long` | `ULONG_MAX` |
| `long long` | `LLONG_MAX` |
| `unsigned long long` | `ULLONG_MAX` |
| `float` | `FLT_MAX` |
| `double` | `DBL_MAX` |

**程序 1:**

下面是说明功能 `std::numeric_limits<T>::max()` 的程序。程序的输出是系统特定的。

```cpp
// C++ program to illustrate the
// function numeric_limits<T>::max
#include <iostream>
#include <limits>
using namespace std;

// Driver Code
int main()
{
    cout << "bool: "
         << numeric_limits<bool>::max()
         << '\n';

    // It returns 127 in ASCII value
    // to print in integer that can
    // be typecast it to int()
    cout << "char: "
         << int(numeric_limits<char>::max())
         << '\n';

    cout << "unsigned char: "
         << int(numeric_limits<unsigned char>::max())
         << '\n';

    cout << "short: "
         << numeric_limits<short>::max()
         << '\n';

    cout << "int: " << numeric_limits<int>::max()
         << '\n';

    cout << "unsigned int: "
         << numeric_limits<unsigned int>::max()
         << '\n';

    cout << "long long: "
         << numeric_limits<long long>::max()
         << '\n';

    cout << "float: "
         << numeric_limits<float>::max()
         << '\n';

    cout << "double: "
         << numeric_limits<double>::max()
         << '\n';

    cout << "size_t: "
         << numeric_limits<size_t>::max()
         << '\n';
}
```

**Output:**
```cpp
bool: 1
char: 127
unsigned char: 255
short: 32767
int: 2147483647
unsigned int: 4294967295
long long: 9223372036854775807
float: 3.40282e+38
double: 1.79769e+308
size_t: 18446744073709551615
```

### std::numeric_limits::min()

`std::numeric_limits<T>::min()` 函数用于获取数值型 `T` 所能表示的最小有限值。所有有界算术类型对类型 `T` 有效。

**头文件:**
```cpp
#include<limits>
```

**模板:**
```cpp
static T min() throw();
static constexpr T min() noexcept;
```

**语法:**
```cpp
std::numeric_limits<T>::min
```

**参数:** 接收任意一种数据类型，即 `T`。

**返回类型:** 根据类型返回预定义的[宏](https://www.geeksforgeeks.org/data-type-ranges-and-their-macros-in-c/)，`true` 或 `default T()`。对于非规范化的浮点类型，`min` 返回最小正规范化值。要查找 `float` 数据类型没有小于它的值，请使用 `numeric_limits::lowest()`。一些标准返回值是:

| Type `t` | `std::numeric_limits<t>::min()` |
| --- | --- |
| `bool` | `false` |
| `char` | `CHAR_MIN` |
| `signed char` | `SCHAR_MIN` |
| `unsigned char` | `0` |
| `wchar_t` | `WCHAR_MIN` |
| `short` | `SHRT_MIN` |
| `int` | `INT_MIN` |
| `unsigned int` | `0` |
| `long` | `LONG_MIN` |
| `unsigned long` | `0` |
| `long long` | `LLONG_MIN` |
| `unsigned long long` | `0` |
| `float` | `FLT_MIN` |
| `double` | `DBL_MIN` |

**程序 2:**

下面是说明功能 `std::numeric_limits<T>::min()` 的程序。程序的输出是系统特定的。

```cpp
// C++ program to illustrate the
// function numeric_limits<T>::min
#include <iostream>
#include <limits>
using namespace std;

// Driver Code
int main()
{
    cout << "bool: "
         << numeric_limits<bool>::min()
         << '\n';

    // numeric_limits<char>::min()
    // returns 127 in ASCII value in
    // integer that can be typecast
    // to int()
    cout << "char: "
         << int(numeric_limits<char>::min())
         << '\n';

    cout << "unsigned char: "
         << int(numeric_limits<unsigned char>::min())
         << '\n';

    cout << "short: "
         << numeric_limits<short>::min() << '\n';

    cout << "int: " << std::numeric_limits<int>::min()
         << '\n';
    cout << "unsigned int: "
         << numeric_limits<unsigned int>::min()
         << '\n';

    cout << "long long: "
         << numeric_limits<long long>::min()
         << '\n';
    cout << "float: "
         << numeric_limits<float>::min()
         << '\n';

    cout << "double: "
         << numeric_limits<double>::min()
         << '\n';

    cout << "size_t: "
         << numeric_limits<size_t>::min()
         << '\n';
}
```

**Output:**
```cpp
bool: 0
char: -128
unsigned char: 0
short: -32768
int: -2147483648
unsigned int: 0
long long: -9223372036854775808
float: 1.17549e-38
double: 2.22507e-308
size_t: 0
```