# c++ 中有符号字符的最大值

> 原文:[https://www . geesforgeks . org/最大带符号字符值/c/](https://www.geeksforgeeks.org/maximum-value-of-signed-char-in-c/)

在本文中，我们将讨论 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中的带符号 char [数据类型](https://www.geeksforgeeks.org/c-data-types/)。

有符号字符数据类型的一些属性包括:

*   它通常用于存储 8 位字符。
*   作为带符号的数据类型，它可以存储正值，也可以存储负值。
*   8 位的大小被占用，其中 1 位用于存储值的符号。
*   可存储在带符号字符数据类型中的最大值通常为 **127、**约为**2<sup>7</sup>–1**(但与[编译器相关](https://www.geeksforgeeks.org/compile-32-bit-program-64-bit-gcc-c-c/))。
*   可存储在带符号字符中的最大值和最小值作为常数存储在 [climits](https://www.geeksforgeeks.org/climits-limits-h-cc/) [头文件](https://www.geeksforgeeks.org/header-files-in-c-cpp-and-its-uses/)中，可分别命名为**SCAR**_**MAX 和 SCAR _ MIN**。
*   可以存储在带符号字符数据类型中的最小值通常为 **-128，**即【**】**左右–**2<sup>7</sup>**(但取决于编译器)。
*   在数据类型的[溢出](https://www.geeksforgeeks.org/overflow-in-arithmetic-addition-in-binary-number-system/)或下溢的情况下，该值被环绕。例如，如果 **-128** 存储在有符号字符数据类型中，并从中减去 1，则该变量中的值将等于 **127。**同样，在溢出的情况下，该值将舍入回 **-128** 。

下面是在 C++ 中获取可以用带符号字符存储的最高值的程序:

## C++

```cpp
// C++ program to obtain the maximum value
// that we can store in signed char
#include <climits>
#include <iostream>
using namespace std;

// Driver Code
int main()
{

    // From the constant of climits
    // header file
    signed char valueFromLimits = SCHAR_MAX;
    cout << "Maximum value from "
         << "climits constant: "
         << (int)valueFromLimits
         << '\n';

    valueFromLimits = SCHAR_MIN;
    cout << "Minimum value from "
         << "climits constant: "
         << (int)valueFromLimits
         << '\n';

    // Using the wrap around property
    // of data types

    // Initialize two variables one
    // value with -1 as previous and
    // one with 0 as present
    signed char previous = -1;
    signed char present = 0;

    // Keep on increasing both values
    // until the present increases to
    // the max limit and wraps around to
    // the negative value i.e., present
    // becomes less the previous value
    while (present > previous) {
        previous++ ;
        present++ ;
    }

    cout << "Maximum value using the "
         << "wrap around property: "
         << (int)previous << '\n';

    cout << "Maximum value using the "
         << "wrap around property: "
         << (int)present;

    return 0;
}
```

**Output:**

```cpp
Maximum value from climits constant: 127
Minimum value from climits constant: -128
Maximum value using the wrap around property: 127
Maximum value using the wrap around property: -128

```