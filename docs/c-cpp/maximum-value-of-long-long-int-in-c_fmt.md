# C++ 中长整型的最大值

> 原文：[https://www.geeksforgeeks.org/maximum-value-of-long-long-int-in-c/](https://www.geeksforgeeks.org/maximum-value-of-long-long-int-in-c/)

在本文中，我们将讨论 C++ 中的 `long long int` [数据类型](https://www.geeksforgeeks.org/c-data-types/)。C++ 中的 `long long int` [数据类型](https://www.geeksforgeeks.org/c-data-types/)用于存储 64 位整数。它是存储整数值最大的数据类型之一，不像正负都有的[无符号长整型](https://www.geeksforgeeks.org/maximum-value-of-unsigned-long-long-int-in-c/)。

## `long long int` 数据类型属性

`long long int` 数据类型的一些属性是：

*   作为一种有符号数据类型，它可以存储正值或负值。
*   占用 64 位大小，其中 1 位用于存储整数的符号。
*   可以存储在长整型数据类型中的最大整数值通常是 **9,223,372,036,854,775,807**，即 **2<sup>63</sup> – 1**。
*   可以存储在 `long long int` 中的最大值作为常量存储在头文件 [`<climits>`](https://www.geeksforgeeks.org/climits-limits-h-cc/) 中，其值为 `LLONG_MAX`。
*   可以存储在长整型数据类型中的最小整数值通常是 **–9,223,372,036,854,775,808**，即 **–2<sup>63</sup>**。
*   当数据类型发生溢出或下溢时，值会环绕。例如，如果 **–9,223,372,036,854,775,808** 被存储在 `long long int` 数据类型中并从中减去 1，该变量中的值将等于 **9,223,372,036,854,775,807**。类似地，在发生溢出的情况下，该值将环绕回 **–9,223,372,036,854,775,808**。

## 示例代码

下面是获取 C++ 中 `long long int` 可以存储的最高值的程序：

```cpp
#include <iostream>
#include <climits>
using namespace std;

int main() {
    cout << "Value from climits constant (maximum): " << LLONG_MAX << endl;
    cout << "Value from climits constant (minimum): " << LLONG_MIN << endl;
    return 0;
}
```

**输出：**

```
Value from climits constant (maximum): 9223372036854775807
Value from climits constant (minimum): -9223372036854775808
```