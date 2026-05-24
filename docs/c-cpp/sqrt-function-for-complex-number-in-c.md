# c++ 中复数的 sqrt()函数

> 原文:[https://www . geesforgeks . org/sqrt-c 中复数函数/](https://www.geeksforgeeks.org/sqrt-function-for-complex-number-in-c/)

sqrt()函数的复杂版本在**复杂**头文件中定义。该函数用于计算复数 z 的平方根，该复数 z 具有沿负实轴切割的分支。

**语法:**

```cpp
template <class T> complex<T>
    sqrt(const complex<T>& z);

```

**参数:**该方法取一个强制参数 **z** ，表示要计算平方根的复数。
**返回值:**该函数返回复数 z 的**平方根**

下面的程序说明了 C++ 中复数的 sqrt()函数:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// example of sqrt() function.

#include <math.h>
#include <iostream>
#include <complex>
using namespace std;

int main()
{
    cout << "Square root of -9 is ";
    cout << sqrt(complex<double>(-9.0, 0.0)) << endl;

    cout << "Square root of (-9, -0) is ";
    cout << sqrt(complex<double>(-9.0, -0.0)) << endl;

    return 0;
}
```

**Output**

```cpp
Square root of -9 is (0,3)
Square root of (-9, -0) is (0,-3)

```