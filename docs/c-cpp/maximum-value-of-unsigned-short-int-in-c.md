# c++ 中无符号短整型的最大值

> 原文:[https://www . geesforgeks . org/最大无符号短整型值-in-c/](https://www.geeksforgeeks.org/maximum-value-of-unsigned-short-int-in-c/)

在本文中，我们将讨论 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中的[无符号短整型数据类型](https://www.geeksforgeeks.org/c-data-types/)。它是 C++ 中最小的(16 位)整数[数据类型。](https://www.geeksforgeeks.org/c-data-types/)

无符号短整型数据类型的一些属性如下:

1.  作为无符号数据类型，它只能存储正值。
2.  取 16 位大小。
3.  可以存储在无符号短整型数据类型中的最大整数值通常为 **65535** ，位于**2<sup>16</sup>–1**附近(但与[编译器相关](https://www.geeksforgeeks.org/compile-32-bit-program-64-bit-gcc-c-c/))。
4.  无符号短整型可存储的最大值作为常量存储在 [< climits >](https://www.geeksforgeeks.org/climits-limits-h-cc/) [头文件](https://www.geeksforgeeks.org/write-header-file-c/)中，其值可用作 **USHRT_MAX** 。
5.  可以存储在无符号短整型中的最小值为零。
6.  在数据类型上溢或下溢的情况下，该值被环绕。例如，如果将 **0** 存储在无符号短整型数据类型中，并从中减去 **1** ，则该变量中的值将等于 **65535** 。同样，在溢出的情况下，该值将舍入回零。

下面是在 C++ 中获取可以用无符号短整型存储的最高值的程序:

## C++

```cpp
// C++ program to obtain the maximum
// value that we can store in an
// unsigned short int
#include <climits>
#include <iostream>
using namespace std;

int main()
{
    // From the constant of climits
    // header file
    unsigned short int valueFromLimits = USHRT_MAX;
    cout << "Value from climits "
         << "constant: "
         << valueFromLimits << "\n";

    // using the wrap around property
    // of data types

    // Initialize variable with value 0
    unsigned short int value = 0;

    // subtract 1 from the value since
    // unsigned data type cannot store
    // negative number, the value will
    // wrap around and store the maximum
    // value that can store in it
    value = value - 1;

    cout << "Value using the wrap "
         << "around property: "
         << value << "\n";

    return 0;
}
```

**Output:**

```cpp
Value from climits constant: 65535
Value using the wrap around property: 65535

```