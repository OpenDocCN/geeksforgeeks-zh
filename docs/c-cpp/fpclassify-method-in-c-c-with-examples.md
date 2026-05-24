# C/c++ 中的 fpclassify()方法，示例

> 原文:[https://www . geeksforgeeks . org/FP classifier-method-in-c-c-with-examples/](https://www.geeksforgeeks.org/fpclassify-method-in-c-c-with-examples/)

**FP classifier()**函数在 C++ 中的 **[math.h 头文件](https://www.geeksforgeeks.org/c-library-math-h-functions/)** 和 **[cmath 库中定义。该函数用于获取与分类宏常量之一相匹配的 int 类型的值(取决于 x 的值)。](https://www.geeksforgeeks.org/c-mathematical-functions/)**

**语法:**

```cpp
int fpclassify(int x);
int fpclassify(float x);
int fpclassify(double x);
int fpclassify(long double x);

```

**参数:**该方法接受一个参数 **x** ，该参数是与该方法的一个宏常数相匹配的值。它可以是整数、浮点、双精度或长双精度。

**返回值:**该函数返回宏常量的整数值，如下所示:

*   **FP_INFINITE** :当指定值为正或负无穷大时
*   **FP_NAN** :当指定值不是数字时
*   **FP_ZERO** :当指定值为零时。
*   **FP_SUBNORMAL** :当指定值为正或负反规格化值时
*   **FP_NORMAL** :当指定值为正或负的归一化非零值时

以下示例演示了 FP classifier()方法的使用:

```cpp
// C++ program to demonstrate
// the use of fpclassify() method

#include <iostream>
#include <math.h>
using namespace std;

// Function to implement fpclassify() method
void fpclassification(double x)
{

    // fpclassify() method
    switch (fpclassify(x)) {

    // For the data to be infinite
    case FP_INFINITE:
        cout << "Infinite Number \n";
        break;

    // For the data to be not defined
    // as in divide by zero
    case FP_NAN:
        cout << "Not a Number \n";
        break;

    // For the data to be zero
    case FP_ZERO:
        cout << "Zero \n";
        break;

    // For the data to be subnormal
    case FP_SUBNORMAL:
        cout << "Subnormal value \n";
        break;

    // For the data to be normal
    case FP_NORMAL:
        cout << "Normal value \n";
        break;

    // For the data to be invalid
    default:
        cout << "Invalid number \n";
    }
}

// Driver code
int main()
{

    // Example 1
    double a = 1.0 / 0.0;
    cout << "For 1.0/0.0: ";
    fpclassification(a);

    // Example 2
    double b = 0.0 / 0.0;
    cout << "For 0.0/0.0: ";
    fpclassification(b);

    // Example 3
    double c = -0.0;
    cout << "For -0.0: ";
    fpclassification(c);

    // Example 4
    double d = 1.0;
    cout << "For 1.0: ";
    fpclassification(d);

    return 0;
}
```

**Output:**

```cpp
For 1.0/0.0: Infinite Number 
For 0.0/0.0: Not a Number 
For -0.0: Zero 
For 1.0: Normal value

```