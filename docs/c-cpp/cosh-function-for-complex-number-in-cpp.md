# c++ 中复数的 cosh()函数

> 原文:[https://www . geeksforgeeks . org/cosh-复杂数字函数-in-cpp/](https://www.geeksforgeeks.org/cosh-function-for-complex-number-in-cpp/)

复数的 **cosh()** 函数在**复数**头文件中定义。该功能是 **cosh()** 功能的复杂版本。该函数用于计算复数 z 的复双曲余弦，并返回复数 z 的 cosh。

**语法:**

```cpp
cosh(z);

```

**参数:**

*   **z:** This method takes a mandatory parameter **z** representing plural numbers.

**返回值:**此函数返回复数 z 的 cosh()

下面的程序说明了 C++ 中的 cosh()函数:

**程序 1:-**

**输出:**

```cpp
The cosh of (0, 1) is (0.540302, 0)

```

**例 2:-**

```cpp

// c++ program to demonstrate
// example of cosh() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main ()
{
  complex<double> complexnumber (1.0, 0.0);

  // use of cosh() function for complex number
  cout << "The cosh of " << complexnumber << " is "
                     << cosh(complexnumber) << endl;

  return 0;
}
```

**输出:**

```cpp
The cosh of (1, 0) is (1.54308, 0)

```