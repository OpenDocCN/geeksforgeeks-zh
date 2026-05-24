# C++ 中短整型的最大值

> 原文:[https://www . geesforgeks . org/max-value-of-short-int-in-c/](https://www.geeksforgeeks.org/maximum-value-of-short-int-in-c/)

在本文中，我们将讨论 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 中的短整型数据类型。C++ 中的这个数据类型用于存储 16 位整数。

短整型数据类型的一些属性包括:

1.  作为带符号的数据类型，它可以存储正值，也可以存储负值。
2.  取 16 位的大小，其中 1 位用于存储整数的符号。
3.  可以存储在短整型数据类型中的最大整数值通常为 `32767`（`2^15 - 1`，但与编译器相关）。
4.  在 [`<climits>`](https://www.geeksforgeeks.org/climits-limits-h-cc/) 头文件中，可存储的最大值以常量形式存储，其值为 `SHRT_MAX`。
5.  在 [`<climits>`](https://www.geeksforgeeks.org/climits-limits-h-cc/) 头文件中，可以用短整型存储的最小值作为常量存储，其值为 `SHRT_MIN`。
6.  可以存储在短整型数据类型中的最小整数值通常为 `-32768`（`-2^15 + 1`，不过是编译器依赖的）。
7.  在数据类型的溢出或下溢的情况下，该值被环绕。例如，如果将 `-32768` 存储在短整型数据类型中，并从中减去 1，则该变量中的值将等于 `32767`。同样，在溢出的情况下，数值会四舍五入回 `-32768`。

下面是获取 C++ 中无符号长整型可以存储的最高值的程序:

## C++

```cpp
// C++ program to obtain the maximum
// value that can be store in short int
#include <climits>
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // From the constant of climits
    // header file
    short int valueFromLimits = SHRT_MAX;
    cout << "Value from climits "
         << "constant (maximum): "
         << valueFromLimits << "\n";

    valueFromLimits = SHRT_MIN;
    cout << "Value from climits "
         << "constant (minimum): "
         << valueFromLimits << "\n";

    // Using the wrap around property
    // of data types

    // Initialize two variables with
    // -1 as previous and 0 as present
    short int previous = -1;
    short int present = 0;

    // Increment both values until the
    // present increases to the max limit
    // and wraps around to the negative
    // value i.e., present becomes less
    // than the previous value
    while (present > previous) {
        previous++ ;
        present++ ;
    }

    cout << "Value using the wrap "
         << " around property :\n";
    cout << "Maximum: " << previous << "\n";
    cout << "Minimum: " << present << "\n";

    return 0;
}
```

**Output:**

```cpp
Value from climits constant (maximum): 32767
Value from climits constant (minimum): -32768
Value using the wrap around property :
Maximum: 32767
Minimum: -32768
```