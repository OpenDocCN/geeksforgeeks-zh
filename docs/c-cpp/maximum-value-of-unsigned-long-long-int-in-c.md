# c++ 中无符号长整型的最大值

> 原文:[https://www . geesforgeks . org/最大值-无符号-long-long-int-in-c/](https://www.geeksforgeeks.org/maximum-value-of-unsigned-long-long-int-in-c/)

在本文中，我们将讨论 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中的**无符号长整型** [数据类型](https://www.geeksforgeeks.org/c-data-types/)。是 C++ 中最大的(64 位)整数[数据类型。](https://www.geeksforgeeks.org/c-data-types/)

无符号长整型数据类型的一些属性包括:

*   无符号数据类型只存储正值。
*   需要 **64** 位的大小。
*   可以存储在无符号长整型数据类型中的最大整数值为 **18，446，744，073，709，551，615，**在**2<sup>64</sup>–1**周围(但与[编译器相关](https://www.geeksforgeeks.org/compile-32-bit-program-64-bit-gcc-c-c/))。
*   无符号长整型可存储的最大值作为常量存储在 [< climits >](https://www.geeksforgeeks.org/climits-limits-h-cc/) [头文件](https://www.geeksforgeeks.org/write-header-file-c/)中，头文件的值可用作 **ULLONG_MAX** 。
*   无符号长整型可以存储的最小值为零。
*   在数据类型的[溢出](https://www.geeksforgeeks.org/overflow-in-arithmetic-addition-in-binary-number-system/)或下溢的情况下，该值被环绕。例如，如果 **0** 存储在无符号长整型数据类型中，并且从中减去 **1** ，则该变量中的值将等于 **18，446，744，073，709，551，615。**同样，在溢出的情况下，该值将舍入回 **0** 。

下面是获取 C++ 中无符号长整型可以存储的最高值的程序:

## C++

```cpp
// C++ program to obtain the maximum
// value stored in unsigned long long int
#include <climits>
#include <iostream>
using namespace std;

// Driver Code
int main()
{

    // From the constant of climits
    // header file
    unsigned long long int valueFromLimits = ULLONG_MAX;

    cout << "Value from climits "
         << "constant: ";
    cout << valueFromLimits << "\n";

    // Using the wrap around property
    // of data types

    // Initialize a variable with value 0
    unsigned long long int value = 0;

    // Subtract 1 from value since an
    // unsigned data type cannot store
    // negative number, the value will
    // wrap around  and stores maximum
    // value stored in it
    value = value - 1;
    cout << "Value using the wrap"
         << " around property: "
         << value << "\n";

    return 0;
}
```

**Output:**

```cpp
Value from climits constant: 18446744073709551615
Value using the wrap around property: 18446744073709551615

```