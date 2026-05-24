# C/c++ 中的 tgamma()方法，示例

> 原文:[https://www . geesforgeks . org/tgamma-method-in-c-c-with-examples/](https://www.geeksforgeeks.org/tgamma-method-in-c-c-with-examples/)

**tgamma()** 函数在 C 中的 [**math.h 头文件**](https://www.geeksforgeeks.org/c-library-math-h-functions/) 和 C++ 中的 [**cmath 库**](https://www.geeksforgeeks.org/c-mathematical-functions/) 中定义。此函数用于计算传递给函数的参数的 gamma 函数。
**语法:**

```cpp
float tgamma(float x);  
double tgamma(double x);  
long double tgamma(long double x);  
```

**参数:**该方法接受参数 **x** ，该参数是要计算其伽马函数的值。它可以是浮点型、双精度型或长双精度型。
**返回值:**该函数返回γ函数值 x.

*   对于 **x = 0** : +inf/-inf
*   对于 **x = -inf** : NAN
*   对于 **x = +inf** : +inf
*   对于 **x = -ve** : NAN
*   对于 **x = NAN** : NAN

**错误:**tgamma()方法通常会出现两种类型的错误:

1.  **范围误差:**
    *   **溢出范围误差**:当参数 x 的幅度很大时会出现这种情况。
    *   **下溢范围误差**:当参数 x 的幅值很小时会出现这种情况。
2.  **域/极点误差:**
    *   如果 x 是零或负整数，且函数是渐近的，则可能导致域误差或极点误差(或无误差，具体取决于实现方式)。

以下示例演示了 tgamma()函数在 C/C++ 中的使用:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to show the
// use of tgamma() method

#include <cmath>
#include <iostream>
using namespace std;

// Driver code
int main()
{

    // Example 1
    float x = 0.0;
    cout << "For x = " << x
         << ", tgamma(x) = "
         << tgamma(x) << endl;

    // Example 2
    x = -18.0 / 0.0;
    cout << "For x = " << x
         << ", tgamma(x) = "
         << tgamma(x) << endl;

    // Example 3
    x = 10.0 / 0.0;
    cout << "For x = " << x
         << ", tgamma(x) = "
         << tgamma(x) << endl;

    // Example 4
    x = 0.0 / 0.0;
    cout << "For x = " << x
         << ", tgamma(x) = "
         << tgamma(x);

    return 0;
}
```

**Output:** 

```cpp
For x = 0, tgamma(x) = inf
For x = -inf, tgamma(x) = nan
For x = inf, tgamma(x) = inf
For x = -nan, tgamma(x) = -nan
```

**参考:**T2http://www.cplusplus.com/reference/cmath/tgamma/