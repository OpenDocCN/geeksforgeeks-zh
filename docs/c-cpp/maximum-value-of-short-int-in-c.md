# c++ 中短整型的最大值

> 原文:[https://www . geesforgeks . org/max-value-of-short-int-in-c/](https://www.geeksforgeeks.org/maximum-value-of-short-int-in-c/)

在本文中，我们将讨论 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中的**短整型数据类型**。C++ 中的这个[数据类型用于存储 16 位整数。](https://www.geeksforgeeks.org/c-data-types/)

短整型数据类型的一些属性包括:

1.  作为带符号的数据类型，它可以存储正值，也可以存储负值。
2.  取 16 位的大小，其中 1 位用于存储整数的符号。
3.  可以存储在短整型数据类型中的最大整数值通常为**32767****围绕**2****<sup>15</sup>****-1**(但与编译器相关)。**
4.  **在 [< climits >](https://www.geeksforgeeks.org/climits-limits-h-cc/) 头文件中，可存储的最大值以常量形式存储。谁的值可以作为T3】SHRT _ MAXT5。**
5.  **在 [< climits >](https://www.geeksforgeeks.org/climits-limits-h-cc/) 头文件中，可以用短整型存储的最小值作为常量存储。谁的值可以作为T3】SHRT _ MINT5。**
6.  **可以存储在短整型数据类型中的最小整数值通常为**-32768******(****)-2<sup>15</sup>+1****)**(不过是[编译器依赖的](https://www.geeksforgeeks.org/compile-32-bit-program-64-bit-gcc-c-c/))。****
7.  ****在数据类型的[溢出](https://www.geeksforgeeks.org/overflow-in-arithmetic-addition-in-binary-number-system/)或下溢的情况下，该值被环绕。例如，如果将 **-32768** 存储在短整型数据类型中，并从中减去 1，则该变量中的值将等于 **32767** **。**同样，在溢出的情况下，数值会四舍五入回 **-32768** 。****

****下面是获取 C++ 中无符号长整型可以存储的最高值的程序:****

## ****C++****

```cpp
**// C++ program to obtain themaximum
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
         << "around property :\n";
    cout << "Maximum: " << previous << "\n";
    cout << "Minimum: " << present << "\n";

    return 0;
}**
```

******Output:**

```cpp
Value from climits constant (maximum): 32767
Value from climits constant (minimum): -32768
Value using the wrap around property :
Maximum: 32767
Minimum: -32768

```****