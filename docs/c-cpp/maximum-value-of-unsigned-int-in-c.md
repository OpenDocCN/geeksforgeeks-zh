# c++ 中无符号整数的最大值

> 原文:[https://www . geesforgeks . org/最大无符号值-int-in-c/](https://www.geeksforgeeks.org/maximum-value-of-unsigned-int-in-c/)

在本文中，我们将讨论 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中无符号 int 的最大值。

*   C++ 中的无符号 int [数据类型](https://www.geeksforgeeks.org/c-data-types/)用于存储 32 位整数。
*   关键字 **无符号** 是一个 [数据类型](https://www.geeksforgeeks.org/data-types-in-c/) 说明符，它只表示非负整数，即正数和零。

无符号 int 数据类型的一些属性包括:

*   无符号数据类型只能存储正值。
*   它需要 32 位的大小。
*   可以存储在无符号 int 数据类型中的最大整数值通常为 **4，294，967，295******2<sup>32</sup>–1**(但与[编译器相关](https://www.geeksforgeeks.org/compile-32-bit-program-64-bit-gcc-c-c/))。**
*   **无符号 int 可以存储的最大值作为常量存储在 [< climits >](https://www.geeksforgeeks.org/climits-limits-h-cc/) 头文件中。其值可以作为 [**UINT** _ **MAX**](https://www.geeksforgeeks.org/int_max-int_min-cc-applications/) 。**
*   **可以存储在无符号整型数据类型中的最小整数值通常为 **0** 。**
*   **在数据类型的[溢出或下溢](https://www.geeksforgeeks.org/check-for-integer-overflow/)的情况下，该值被环绕。**
*   **例如，如果将 **0** 存储在 int 数据类型中，并从中减去 **1** ，则该变量中的值将等于 **4，294，967，295** **。**同样，在[溢出](https://www.geeksforgeeks.org/check-for-integer-overflow/)的情况下，该值将舍入回 **0** 。**

**下面是在 C++ 中获取可以用无符号 int 存储的最高值的程序:**

## **C++**

```cpp
// C++ program to obtain the maximum
// value stored in unsigned int
#include <climits>
#include <iostream>
using namespace std;

// Function that prints the maximum
// value stored in unsigned int
void maxUnsignedInt()
{
    // From the constant of climits
    // header file
    unsigned int valueFromLimits = UINT_MAX;

    cout << "Value from climits constant : "
         << valueFromLimits << "\n";

    // Using the wrap around property
    // of data types

    // Initialize a variable with 0
    unsigned int value = 0;

    // Subtract 1 from value since
    // unsigned data type cannot store
    // negative number, the value will
    // wrap around and store the
    // maximum value in it
    value = value - 1;

    cout << "Value using the wrap"
         << " around property : "
         << value << "\n";
}

// Driver Code
int main()
{
    // Function call
    maxUnsignedInt();

    return 0;
}
```

****Output:**

```cpp
Value from climits constant : 4294967295
Value using the wrap around property : 4294967295

```**