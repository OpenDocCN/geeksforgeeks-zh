# c++

中的 std::numeric_limits::max()和 std::numeric_limits::min()

> 原文:[https://www . geesforgeks . org/stdnumeric _ limitsmax-and-stdnumeric _ limitsmin-in-c/](https://www.geeksforgeeks.org/stdnumeric_limitsmax-and-stdnumeric_limitsmin-in-c/)

### <u>STD::numeric _ limits::max()</u>:

STD::numeric _ limits<T>:max()函数用于获取数值类型 **T** 所能表示的最大有限值。所有算术类型对类型 **T** 有效。

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

**参数:**接收任意一种数据类型，即 **T** 。

**返回类型:**返回预定义的[宏](https://www.geeksforgeeks.org/data-type-ranges-and-their-macros-in-c/)， true 或 default T()取决于类型 T .一些标准返回值为:

<figure class="table">T22】boolT30】CHAR _ MAXT32T34】有符号 CHART36】SCHAR _ MAXT38无符号 CHART42】UCHAR _ MAXT45T48】WCHAR _ MAX【 T80】LONG _ MAXT82T84】无符号长 T86】ULONG _ MAXT88长T92】LLONG _ MAXT94T96】无符号长 T98】ULLONG _ MAXT100T102】浮动 T104

| Type t | 标准::数值限制<t>:最大值()</t> |
| --- | --- |
| /* Non-dedicated */ | t() |
| 真实的 |
| 茶 |
| WCHAR _ t | long |
| long |

</figure>

**程序 1:**

下面是说明功能**STD::numeric _ limits<T>::max()**的程序。程序的输出是系统特定的。

## C++

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

### **<u>标准::数值 _ 限值::分钟()</u> :**

**STD::numeric _ limits<T>:【min()】**函数用于获取数值型 **T** 所能表示的最小有限值。所有有界算术类型对类型 **T** 有效。

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

**参数:**接收任意一种数据类型，即 **T** 。

**返回类型:**根据类型**返回预定义的[宏](https://www.geeksforgeeks.org/data-type-ranges-and-their-macros-in-c/)，真或缺省的 T()**。对于非规范化的浮点类型，min 返回最小正规范化值。要查找[浮动数据类型](https://www.geeksforgeeks.org/c-data-types/)没有小于它的值，请使用 **numeric_limits::最低()** 。一些标准返回值是:

<figure class="table">T34T38】CHAR _ MINT40T42】有符号 CHART44】SCHAR _ MINT46无符号 CHART50】0T52T54】WCHAR _ tT56】WCHAR _ MIN【T57 T88】LONG _ MINT90T92】无符号长 T94】0T96T98】长 T100】LLONG _ MINT102T104】无符号长 T106】0T108T110】浮动 T112】FLT _ MIN【

| T type | 标准::数值 _ 限值::最小值() |
| --- | --- |
| /* Non-dedicated */ | t() |
| 弯曲件 | 错误的 |
| 茶 |
| long |

</figure>

**程序 2:**

下面是说明功能**STD::numeric _ limits<T>:min()**的程序。程序的输出是系统特定的。

## C++

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

    // numeric_limits<char>:: min()
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