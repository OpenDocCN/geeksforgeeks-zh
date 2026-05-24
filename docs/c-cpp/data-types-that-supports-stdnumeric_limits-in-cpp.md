# 支持 C++ 中 std::numeric_limits()的数据类型

> 原文:[https://www . geesforgeks . org/data-type-of-support-stdnumeric _ limits-in-CPP/](https://www.geeksforgeeks.org/data-types-that-supports-stdnumeric_limits-in-cpp/)

[numeric_limits](https://www.geeksforgeeks.org/stdnumeric_limitsmax-and-stdnumeric_limitsmin-in-c/) 类模板提供了一种简单且标准化的方式来查询算术类型的各种属性。例如，一个类型 T 可以存储的最大值是**标准::数值 _ 限制< T >:最大值()**。

**示例:**

*   **STD:: numeric _ limits < int >:: max ()** gives the maximum possible value that we can store in the int type.
*   **STD:: numeric _ limits < unsigned int >:: max ())** gives the maximum possible value that we can store in the unsigned int type.

**numeric_limits** 有许多成员函数、成员常量和助手[类](https://www.geeksforgeeks.org/classes-objects-java/)，其中一些是特定于类型的。例如**标准::数值 _ 限制< T >:最低()**仅适用于浮动数据类型。最常见的数据类型查询有:

*   **STD:: numeric _ limits < T >:: IS _ integer:** If T is a numeric type, it is true, and the floating-point type is false.
*   **STD:: numeric _ limits < T >: IS _ signed:** All signed arithmetic types T are true and unsigned types are false.
*   **STD:: numeric _ limits < T >:: Number of digits:** is the number of digits based on radix. For example -1 stands for bool, 7 for char, 31 for int, etc.
*   **STD:: numeric _ limits < t >:: digits 10:** is the cardinal number -10 digits that can be expressed by T-type, without any change.
*   **STD:: numeric _ limits < T >:: Max _ digits 10:** It is the cardinality -10 digits necessary to uniquely represent all different values of type T.
*   In addition, the minimum value, maximum value, minimum value, byte size and bit are queried.

浮点具有与ε相关的查询。除此之外，**numeric _ limited**还有一些功能。**例如:** **有 _infinity** 、**陷阱**、 **round_error** 等。

下面是显示所有数据类型最常见的 **numeric_limits** 函数的程序:

## c++

```cpp
// C++ program to demonstrate the use
// possible numerical data types
// that supports std::numeric_limits

#include <cstdint>
#include <functional>
#include <iomanip>
#include <iostream>
#include <limits>
#include <string>

struct RowPrinter {
    // Left alignment
    int m_left;

    // Right alignment
    int m_right;
    RowPrinter(int left, int right)
        : m_left(left), m_right(right)
    {
        // Print bool as 'true' or 'false'
        // instead of 0 or 1.
        std::cout << std::boolalpha;
    }

    template <class A>
    auto printRow(const std::string& label,
                  const A& value) const -> void
    {
        std::cout << std::setw(m_left) << label
                  << std::setw(m_right) << value << "\n";
    }
};

#define SHOW_INTEGER_LIMITS(numtype) \
    showNumericLimits<numtype>(#numtype)
#define SHOW_FLOAT_LIMITS(numtype) \
    showFloatPointLimits<numtype>(#numtype)

// Function to show the numeric
// limits
template <class T>
void showNumericLimits(const std::string& name)
{
    RowPrinter rp{ 30, 25 };
    std::cout << "Numeric limits for type: " << name
              << "\n";
    std::cout << std::string(60, '-') << "\n";

    rp.printRow("Type:", name);
    rp.printRow("Is integer:",
                std::numeric_limits<T>::is_integer);

    rp.printRow("Is signed:",
                std::numeric_limits<T>::is_signed);

    rp.printRow("Number of digits:",
                std::numeric_limits<T>::digits);

    rp.printRow("Number of digits 10:",
                std::numeric_limits<T>::digits10);

    rp.printRow("Max Number of digits 10:",
                std::numeric_limits<T>::max_digits10);

    // RTTI - Run-Time Type Information
    if (typeid(T) == typeid(uint8_t)
        || typeid(T) == typeid(int8_t)
        || typeid(T) == typeid(bool)
        || typeid(T) == typeid(char)
        || typeid(T) == typeid(unsigned char)) {

        // Min Abs - smallest positive value
        // for float point numbers
        rp.printRow("Min:",
                    static_cast<int>(
                        std::numeric_limits<T>::min()));

        // Smallest value (can be negative)
        rp.printRow("Lowest:",
                    static_cast<int>(
                        std::numeric_limits<T>::lowest()));

        // Largest value
        rp.printRow("Max:",
                    static_cast<int>(
                        std::numeric_limits<T>::max()));
    }

    else {
        rp.printRow("Min:", std::numeric_limits<T>::min());
        rp.printRow("Lowest:",
                    std::numeric_limits<T>::lowest());
        rp.printRow("Max:", std::numeric_limits<T>::max());
    }

    rp.printRow("Size in bytes:", sizeof(T));
    rp.printRow("Size in bits:", 8 * sizeof(T));
    std::cout << "\n";
}

// Function to show float points
// limits
template <class T>
void showFloatPointLimits(const std::string& name)
{
    RowPrinter rp{ 30, 25 };
    showNumericLimits<T>(name);
    rp.printRow("Epsilon:",
                std::numeric_limits<T>::epsilon());
    rp.printRow("Min exponent:",
                std::numeric_limits<T>::min_exponent10);
    rp.printRow("Max exponent:",
                std::numeric_limits<T>::max_exponent10);
}

// Driver Code
int main()
{
    // Boolean type
    SHOW_INTEGER_LIMITS(bool);

    // Character types
    SHOW_INTEGER_LIMITS(char);
    SHOW_INTEGER_LIMITS(unsigned char);
    SHOW_INTEGER_LIMITS(wchar_t);

    // Standard integers in <cstdint>
    SHOW_INTEGER_LIMITS(int8_t);
    SHOW_INTEGER_LIMITS(uint8_t);
    SHOW_INTEGER_LIMITS(int16_t);
    SHOW_INTEGER_LIMITS(uint16_t);
    SHOW_INTEGER_LIMITS(int32_t);
    SHOW_INTEGER_LIMITS(uint32_t);
    SHOW_INTEGER_LIMITS(int64_t);
    SHOW_INTEGER_LIMITS(uint64_t);

    // Integer types
    SHOW_INTEGER_LIMITS(short);
    SHOW_INTEGER_LIMITS(unsigned short);
    SHOW_INTEGER_LIMITS(int);
    SHOW_INTEGER_LIMITS(unsigned int);
    SHOW_INTEGER_LIMITS(long);
    SHOW_INTEGER_LIMITS(unsigned long);
    SHOW_INTEGER_LIMITS(long long);
    SHOW_INTEGER_LIMITS(unsigned long long);

    // Floating types
    SHOW_FLOAT_LIMITS(float);
    SHOW_FLOAT_LIMITS(double);
    SHOW_FLOAT_LIMITS(long double);

    return 0;
}
```

**输出:**

```cpp
Numeric limits for type: bool
------------------------------------------------------------
                         Type:                     bool
                   Is integer:                     true
                    Is signed:                    false
             Number of digits:                        1
          Number of digits 10:                        0
      Max Number of digits 10:                        0
                          Min:                        0
                       Lowest:                        0
                          Max:                        1
                Size in bytes:                        1
                 Size in bits:                        8

Numeric limits for type: char
------------------------------------------------------------
                         Type:                     char
                   Is integer:                     true
                    Is signed:                     true
             Number of digits:                        7
          Number of digits 10:                        2
      Max Number of digits 10:                        0
                          Min:                     -128
                       Lowest:                     -128
                          Max:                      127
                Size in bytes:                        1
                 Size in bits:                        8

Numeric limits for type: unsigned char
------------------------------------------------------------
                         Type:            unsigned char
                   Is integer:                     true
                    Is signed:                    false
             Number of digits:                        8
          Number of digits 10:                        2
      Max Number of digits 10:                        0
                          Min:                        0
                       Lowest:                        0
                          Max:                      255
                Size in bytes:                        1
                 Size in bits:                        8

Numeric limits for type: wchar_t
------------------------------------------------------------
                         Type:                  wchar_t
                   Is integer:                     true
                    Is signed:                     true
             Number of digits:                       31
          Number of digits 10:                        9
      Max Number of digits 10:                        0
                          Min:              -2147483648
                       Lowest:              -2147483648
                          Max:               2147483647
                Size in bytes:                        4
                 Size in bits:                       32

Numeric limits for type: int8_t
------------------------------------------------------------
                         Type:                   int8_t
                   Is integer:                     true
                    Is signed:                     true
             Number of digits:                        7
          Number of digits 10:                        2
      Max Number of digits 10:                        0
                          Min:                     -128
                       Lowest:                     -128
                          Max:                      127
                Size in bytes:                        1
                 Size in bits:                        8

Numeric limits for type: uint8_t
------------------------------------------------------------
                         Type:                  uint8_t
                   Is integer:                     true
                    Is signed:                    false
             Number of digits:                        8
          Number of digits 10:                        2
      Max Number of digits 10:                        0
                          Min:                        0
                       Lowest:                        0
                          Max:                      255
                Size in bytes:                        1
                 Size in bits:                        8

Numeric limits for type: int16_t
------------------------------------------------------------
                         Type:                  int16_t
                   Is integer:                     true
                    Is signed:                     true
             Number of digits:                       15
          Number of digits 10:                        4
      Max Number of digits 10:                        0
                          Min:                   -32768
                       Lowest:                   -32768
                          Max:                    32767
                Size in bytes:                        2
                 Size in bits:                       16

Numeric limits for type: uint16_t
------------------------------------------------------------
                         Type:                 uint16_t
                   Is integer:                     true
                    Is signed:                    false
             Number of digits:                       16
          Number of digits 10:                        4
      Max Number of digits 10:                        0
                          Min:                        0
                       Lowest:                        0
                          Max:                    65535
                Size in bytes:                        2
                 Size in bits:                       16

Numeric limits for type: int32_t
------------------------------------------------------------
                         Type:                  int32_t
                   Is integer:                     true
                    Is signed:                     true
             Number of digits:                       31
          Number of digits 10:                        9
      Max Number of digits 10:                        0
                          Min:              -2147483648
                       Lowest:              -2147483648
                          Max:               2147483647
                Size in bytes:                        4
                 Size in bits:                       32

Numeric limits for type: uint32_t
------------------------------------------------------------
                         Type:                 uint32_t
                   Is integer:                     true
                    Is signed:                    false
             Number of digits:                       32
          Number of digits 10:                        9
      Max Number of digits 10:                        0
                          Min:                        0
                       Lowest:                        0
                          Max:               4294967295
                Size in bytes:                        4
                 Size in bits:                       32

Numeric limits for type: int64_t
------------------------------------------------------------
                         Type:                  int64_t
                   Is integer:                     true
                    Is signed:                     true
             Number of digits:                       63
          Number of digits 10:                       18
      Max Number of digits 10:                        0
                          Min:     -9223372036854775808
                       Lowest:     -9223372036854775808
                          Max:      9223372036854775807
                Size in bytes:                        8
                 Size in bits:                       64

Numeric limits for type: uint64_t
------------------------------------------------------------
                         Type:                 uint64_t
                   Is integer:                     true
                    Is signed:                    false
             Number of digits:                       64
          Number of digits 10:                       19
      Max Number of digits 10:                        0
                          Min:                        0
                       Lowest:                        0
                          Max:     18446744073709551615
                Size in bytes:                        8
                 Size in bits:                       64

Numeric limits for type: short
------------------------------------------------------------
                         Type:                    short
                   Is integer:                     true
                    Is signed:                     true
             Number of digits:                       15
          Number of digits 10:                        4
      Max Number of digits 10:                        0
                          Min:                   -32768
                       Lowest:                   -32768
                          Max:                    32767
                Size in bytes:                        2
                 Size in bits:                       16

Numeric limits for type: unsigned short
------------------------------------------------------------
                         Type:           unsigned short
                   Is integer:                     true
                    Is signed:                    false
             Number of digits:                       16
          Number of digits 10:                        4
      Max Number of digits 10:                        0
                          Min:                        0
                       Lowest:                        0
                          Max:                    65535
                Size in bytes:                        2
                 Size in bits:                       16

Numeric limits for type: int
------------------------------------------------------------
                         Type:                      int
                   Is integer:                     true
                    Is signed:                     true
             Number of digits:                       31
          Number of digits 10:                        9
      Max Number of digits 10:                        0
                          Min:              -2147483648
                       Lowest:              -2147483648
                          Max:               2147483647
                Size in bytes:                        4
                 Size in bits:                       32

Numeric limits for type: unsigned int
------------------------------------------------------------
                         Type:             unsigned int
                   Is integer:                     true
                    Is signed:                    false
             Number of digits:                       32
          Number of digits 10:                        9
      Max Number of digits 10:                        0
                          Min:                        0
                       Lowest:                        0
                          Max:               4294967295
                Size in bytes:                        4
                 Size in bits:                       32

Numeric limits for type: long
------------------------------------------------------------
                         Type:                     long
                   Is integer:                     true
                    Is signed:                     true
             Number of digits:                       63
          Number of digits 10:                       18
      Max Number of digits 10:                        0
                          Min:     -9223372036854775808
                       Lowest:     -9223372036854775808
                          Max:      9223372036854775807
                Size in bytes:                        8
                 Size in bits:                       64

Numeric limits for type: unsigned long
------------------------------------------------------------
                         Type:            unsigned long
                   Is integer:                     true
                    Is signed:                    false
             Number of digits:                       64
          Number of digits 10:                       19
      Max Number of digits 10:                        0
                          Min:                        0
                       Lowest:                        0
                          Max:     18446744073709551615
                Size in bytes:                        8
                 Size in bits:                       64

Numeric limits for type: long long
------------------------------------------------------------
                         Type:                long long
                   Is integer:                     true
                    Is signed:                     true
             Number of digits:                       63
          Number of digits 10:                       18
      Max Number of digits 10:                        0
                          Min:     -9223372036854775808
                       Lowest:     -9223372036854775808
                          Max:      9223372036854775807
                Size in bytes:                        8
                 Size in bits:                       64

Numeric limits for type: unsigned long long
------------------------------------------------------------
                         Type:       unsigned long long
                   Is integer:                     true
                    Is signed:                    false
             Number of digits:                       64
          Number of digits 10:                       19
      Max Number of digits 10:                        0
                          Min:                        0
                       Lowest:                        0
                          Max:     18446744073709551615
                Size in bytes:                        8
                 Size in bits:                       64

Numeric limits for type: float
------------------------------------------------------------
                         Type:                    float
                   Is integer:                    false
                    Is signed:                     true
             Number of digits:                       24
          Number of digits 10:                        6
      Max Number of digits 10:                        9
                          Min:              1.17549e-38
                       Lowest:             -3.40282e+38
                          Max:              3.40282e+38
                Size in bytes:                        4
                 Size in bits:                       32

                      Epsilon:              1.19209e-07
                 Min exponent:                      -37
                 Max exponent:                       38
Numeric limits for type: double
------------------------------------------------------------
                         Type:                   double
                   Is integer:                    false
                    Is signed:                     true
             Number of digits:                       53
          Number of digits 10:                       15
      Max Number of digits 10:                       17
                          Min:             2.22507e-308
                       Lowest:            -1.79769e+308
                          Max:             1.79769e+308
                Size in bytes:                        8
                 Size in bits:                       64

                      Epsilon:              2.22045e-16
                 Min exponent:                     -307
                 Max exponent:                      308
Numeric limits for type: long double
------------------------------------------------------------
                         Type:              long double
                   Is integer:                    false
                    Is signed:                     true
             Number of digits:                       64
          Number of digits 10:                       18
      Max Number of digits 10:                       21
                          Min:             3.3621e-4932
                       Lowest:           -1.18973e+4932
                          Max:            1.18973e+4932
                Size in bytes:                       16
                 Size in bits:                      128

                      Epsilon:               1.0842e-19
                 Min exponent:                    -4931
                 Max exponent:                     4932
```