# c++ 中无符号字符的最大值

> 原文:[https://www . geesforgeks . org/无符号字符的最大值/c/](https://www.geeksforgeeks.org/maximum-value-of-unsigned-char-in-c/)

在本文中，我们将讨论 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中无符号字符[数据类型](https://www.geeksforgeeks.org/c-data-types/)的最大值。

[无符号字符](https://www.geeksforgeeks.org/unsigned-char-in-c-with-examples/)数据类型的一些属性包括:

*   作为无符号数据类型，它只能存储正值。
*   C++ 中的无符号字符[数据类型](https://www.geeksforgeeks.org/c-data-types/)用于存储 8 位字符。
*   可以存储在无符号字符数据类型中的最大值通常为 **255、**约为**2<sup>8</sup>–1**(但取决于编译器)。
*   可以存储在无符号字符中的最大值作为常量存储在 [< climits >](https://www.geeksforgeeks.org/climits-limits-h-cc/) 头文件中，其值可以用作 **UCHAR** _ **MAX。**
*   可以存储在无符号字符数据类型中的最小值是 **0** 。
*   在数据类型的[溢出或下溢](https://www.geeksforgeeks.org/check-for-integer-overflow/)的情况下，该值被环绕。
*   例如，如果 **0** 存储在无符号字符数据类型中，并从中减去 1，则该变量中的值将等于 **255。**同样，在溢出的情况下，该值将舍入回 **0** 。

下面是在 C++ 中获取可以用无符号字符存储的最高值的程序:

## C++

```cpp
// C++ program to obtain the maximum
// value that can be stored in an
// unsigned char

#include <climits>
#include <iostream>
using namespace std;

// Function to find the maximum value
// stored in unsigned char
void maxUnsignedChar()
{
    // From the constant of climits
    // header file
    unsigned char valueFromLimits = UCHAR_MAX;
    cout << "Value from climits "
         << "constant : "
         << (int)valueFromLimits
         << "\n";

    // Using the wrap around property
    // of data types

    // Initialize a variable with
    // value 0
    unsigned char value = 0;

    // Subtract 1 from value since
    // unsigned data type cannot store
    // negative number, the value will
    // wrap around and store the maximum
    // value that we can store in it
    value = value - 1;

    cout << "Value using the wrap "
         << "around property : "
         << (int)value << "\n";
}

// Driver Code
int main()
{
    // Function call
    maxUnsignedChar();

    return 0;
}
```

**Output:**

```cpp
Value from climits constant : 255
Value using the wrap around property : 255

```