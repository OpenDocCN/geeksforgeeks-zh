# c++ 中长整型的最大值

> 原文:[https://www . geesforgeks . org/long-long-int-in-c 最大值/](https://www.geeksforgeeks.org/maximum-value-of-long-long-int-in-c/)

在本文中，我们将讨论 C++ 中的 long long int [数据类型](https://www.geeksforgeeks.org/c-data-types/)。C++ 中的 long long int [数据类型](https://www.geeksforgeeks.org/c-data-types/)用于存储 64 位整数。它是存储整数值最大的数据类型之一，不像正负都有的[无符号长整型](https://www.geeksforgeeks.org/maximum-value-of-unsigned-long-long-int-in-c/)。

long long int 数据类型的一些属性是:

*   As a signed data type, it can store positive or negative values.
*   Take the size of 64 bits, of which 1 bit is used to store the symbol of the integer.
*   The maximum integer value that can be stored in a long integer data type is usually **9, 223, 372, 036, 854, 775, 807** at **2 <sup>63</sup> –1**
*   The maximum value that can be stored long long int is stored as a constant in the header file of [< cilimits >](https://www.geeksforgeeks.org/climits-limits-h-cc/) . Whose value can be ****llong _ max** ?**
***   The minimum integer value that can be stored in a long integer data type is usually around– **9,223,372,036,854,775,808** **and** – **2 <sup>63</sup>***   When the data type overflows or underflows, the values are surrounded. For example, if– **9,223,372,036,854,775,808** is stored in the long long int data type and 1 is subtracted from it, the value in this variable will be equal to **9,223,372,000\. Similarly, in case of overflow, this value will be rounded back to– **9, 223, 372, 036, 854, 775, 808** .****

**下面是获取 C++ 中【long int 可以存储的最高值的程序:**

**T5【c++ T0****T10**输出:**

```cpp
Value from climits constant (maximum): 9223372036854775807
Value from climits constant (minimum): -9223372036854775808

```

T13】**