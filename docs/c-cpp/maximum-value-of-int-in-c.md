# c++ 中 int 的最大值

> 原文:[https://www.geeksforgeeks.org/maximum-value-of-int-in-c/](https://www.geeksforgeeks.org/maximum-value-of-int-in-c/)

在本文中，我们将讨论 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中的 **int** [数据类型](https://www.geeksforgeeks.org/c-data-types/)。用于存储 **32 位整数**。

**int** 数据类型的一些属性包括:

*   作为带符号的数据类型，它可以存储正值，也可以存储负值。
*   取 **32 位**的大小，其中 **1 位**用于存储整数的符号。
*   可以存储在 **int** 数据类型中的最大整数值通常是 **2，147，483，647** ，位于**2<sup>31</sup>–1**周围，但与[编译器相关](https://www.geeksforgeeks.org/compile-32-bit-program-64-bit-gcc-c-c/)。
*   可以存储在 **int** 中的最大值作为常量存储在 [< climits >](https://www.geeksforgeeks.org/climits-limits-h-cc/) [头文件](https://www.geeksforgeeks.org/write-header-file-c/)中，头文件的值可以作为[**INT**_**MAX**](https://www.geeksforgeeks.org/int_max-int_min-cc-applications/)。
*   可以存储在 int 数据类型中的最小整数值通常为 **-2，147，483，648** **，**在 **-2 <sup>31</sup>** 周围，但与编译器有关。
*   在数据类型的[溢出](https://www.geeksforgeeks.org/check-for-integer-overflow/)或[下溢](https://www.geeksforgeeks.org/check-for-integer-overflow/)的情况下，该值被环绕。例如，如果将 **-2，147，483，648** 存储在 **int** 数据类型中，并从中减去 **1** ，则该变量中的值将等于 **2，147，483，647** **。**同样，在溢出的情况下，该值将舍入回 **-2，147，483，648** 。

下面是在 C++ 中获取 int 中可以存储的最高值的程序:

## C++

```cpp
// C++ program to obtain the maximum
// value that can be store in int
#include <climits>
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // From the constant of climits
    // header file
    int valueFromLimits = INT_MAX;

    cout << "Value from climits "
         << "constant (maximum): ";
    cout << valueFromLimits << "\n";

    valueFromLimits = INT_MIN;
    cout << "Value from climits "
         << "constant(minimum): ";
    cout << valueFromLimits << "\n";

    // Using the wrap around property
    // of data types

    // Initialize two variables with
    // value -1 as previous and another
    // with 0 as present
    int previous = -1;
    int present = 0;

    // Keep on increasing both values
    // until the present increases to
    // the max limit and wraps around
    // to the negative value i.e., present
    // becomes less than previous value
    while (present > previous) {
        previous++ ;
        present++ ;
    }

    cout << "\nValue using the wrap "
         << "around property:\n";

    cout << "Maximum: " << previous << "\n";
    cout << "Minimum: " << present << "\n";

    return 0;
}
```

**Output:**

```cpp
Value from climits constant (maximum): 2147483647
Value from climits constant(minimum): -2147483648

Value using the wrap around property:
Maximum: 2147483647
Minimum: -2147483648

```