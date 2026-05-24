# _ _ 内置 _ INF()GCC 编译器的功能

> 原文:[https://www . geesforgeks . org/_ _ builtin _ INF-functions-of-gcc-compiler/](https://www.geeksforgeeks.org/__builtin_inf-functions-of-gcc-compiler/)

这些功能**不需要包含任何头文件就可以使用**。所以它提供了**更快的使用**，因为这些是 [GCC 编译器](https://www.geeksforgeeks.org/builtin-functions-gcc-compiler/)的内置函数，这是最常用的编译器，即使在竞争性编程中。

**注意:如果编译器显示溢出警告，在 __builtin_inf()函数之前使用** [**铸造**](https://www.geeksforgeeks.org/type-conversion-c/) **作为**

```cpp
(data_type)__builtin_inf()
```

**1。__builtin_inf(void)** :这个函数返回正无穷大，然后转换成 C 语言 limits.h 头文件 Macro 的 DBL_MAX。它的返回数据类型是 double。

**示例:**

```cpp
if __builtin_inf() is used
it returns infinite

Output: inf
```

下面是一个 C++ 程序，展示了这个函数的用法:

## C++

```cpp
#include <iostream>
using namespace std;

int main()
{
    // infinite value (<b>inf</b>)
    double double_inf = __builtin_inf();

    cout << double_inf << endl;
    return 0;
}
```

**Output:** 

```cpp
inf
```

**2。__builtin_infd32(void)** :此函数返回 4 字节整数的最大值，返回的数据类型为 32 位整数。

**示例:**

```cpp
if __builtin_infd32() is used
it returns the maximum value of
the 32-bit integer

Output: 2147483647
```

下面是一个 C++ 程序，展示了这个函数的用法:

## C++

```cpp
#include <iostream>
using namespace std;

int main()
{
    // function returns highest signed integer value
    int int_inf = (int)__builtin_infd32();

    // you can use __builtin_inf() function
    // as well and then cast to integer
    int int_inf2 = (int)__builtin_inf();

    cout << int_inf << endl;
    cout << int_inf2 << endl;

    // function returns highest unsigned integer value
    unsigned int unsinged_int_inf
        = (unsigned int)__builtin_infd32();

    // you can use __builtin_inf() function as well
    // and then cast to unsigned integer
    unsigned int unsinged_int_inf2
        = (unsigned int)__builtin_inf();

    cout << unsinged_int_inf << endl;
    cout << unsinged_int_inf2 << endl;

    return 0;
}
```

**Output:** 

```cpp
2147483647
2147483647
4294967295
4294967295
```

**3。__builtin_infd64(void)** :这个函数返回最高值，可以用 8 字节整数来表示，这是我们在 C++ 中可以使用的最高整数值。

**示例:**

```cpp
if __builtin_infd64() is used
it returns the maximum value of
the 64-bit integer

Output: 9223372036854775807
```

下面是一个 C++ 程序，展示了这个函数的用法:

## C++

```cpp
#include <iostream>
using namespace std;

int main()
{
    // highest signed 8 byte value
    long long int long_inf = (long long int)__builtin_infd64();

    // you can use __builtin_inf() as well
    // and then cast to long long int
    long long int long_inf2
        = (long long int)__builtin_inf();

    cout << long_inf << endl;
    cout << long_inf2 << endl;

    // highest unsigned 8 byte value
    unsigned long long int unsigned_longlong_inf
        = (unsigned long long int)__builtin_infd64();

    // you can use __builtin_inf() as well
    // and then cast to unsigned long long int
    unsigned long long int unsigned_longlong_inf2
        = (unsigned long long int)__builtin_inf();

    cout << unsigned_longlong_inf << endl;
    cout << unsigned_longlong_inf2 << endl;
    return 0;
}
```

**Output:** 

```cpp
9223372036854775807
9223372036854775807
18446744073709551615
18446744073709551615
```

**4。__builtin_infd128(void)** :由于在 C/C++ 中整数可以使用的最大大小是 64 位，所以这个函数给出的结果与 __builtin_infd64()相同。

**示例:**

```cpp
if __builtin_infd128() is used
it returns the maximum value of
the 64-bit integer

Output: 9223372036854775807
```

**5。__builtin_inff(void)** :此函数返回的浮点最大值表示 4 字节的最大小数点值。

**示例:**

```cpp
if __builtin_inff() is used
it returns the maximum value of
the 32-bit float

Output: inf
```

下面是一个 C++ 程序，展示了这个函数的用法:

## C++

```cpp
#include <iostream>
using namespace std;

int main()
{
    float float_inf = __builtin_inff();

    // you can use __builtin_inf() as well
    // and then cast it to float data type
    float float_inf2 = (float)__builtin_inf();

    cout << float_inf << endl;
    cout << float_inf2 << endl;
    return 0;
}
```

**Output:** 

```cpp
inf
inf
```

**6。__builtin_infl(void)** :此函数返回最大长双精度数据类型值。

**示例:**

```cpp
if __builtin_infl() is used
it returns the maximum value of
the long double type

Output: inf
```

下面是一个 C++ 程序，展示了这个函数的用法:

## C++

```cpp
#include <iostream>
using namespace std;

int main()
{
    long double long_double_inf = __builtin_infl();

    // you can use __builtin_inf() as well
    // and then cast it to float data type
    long double long_double_inf2
        = (long double)__builtin_inf();

    cout << long_double_inf << endl;
    cout << long_double_inf2 << endl;
    return 0;
}
```

**Output:** 

```cpp
inf
inf
```

7.在 GCC 编译器的最新版本中，这是两个新的函数:**_ _ builtin _ infn(void)&_ _ builtin _ infnx(void)**。可以用 **32** 或 **64** 代替 **n** ，分别返回 32 位、64 位的 **inf 值**。

**类似文章:** [**内置 GCC 编译器功能**](https://www.geeksforgeeks.org/builtin-functions-gcc-compiler/)