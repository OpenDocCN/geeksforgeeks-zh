# cos()函数在 C++ 中为复数

> 原文:[https://www . geeksforgeeks . org/cos-function-for-complex-number-in-CPP/](https://www.geeksforgeeks.org/cos-function-for-complex-number-in-cpp/)

复数的 **cos()** 函数在**复数**头文件中定义。该功能是 **cos()** 功能的复杂版本。这个函数用来计算复数 z 的复余弦，这个函数返回复数 z 的 cos。

**语法:**

```cpp
cos (z);

```

**参数:**

*   **z:** 该方法取一个代表复数的强制参数 **z** 。

**返回值:**此函数返回复数 z 的 cos()

下面的程序说明了 C++ 中的 cos()函数:

**程序 1:-**

```cpp
// C++ program to demonstrate
// example of cos() function.
#include <iostream>
#include <complex>
using namespace std;

// driver program
int main ()
{
  complex<double> complexnumber (0.0, 1.0);

  // use of cos() function for complex number
  cout << "The cos of " << complexnumber << " is "
                     << cos(complexnumber) <<endl;

  return 0;
}
```

**Output:**

```cpp
The cos of (0,1) is (1.54308,-0)

```

**程序 2:-**

```cpp
// C++ program to demonstrate
// example of cos() function.
#include <iostream>
#include <complex>
using namespace std;

// driver program
int main ()
{
  complex<double> complexnumber (1.0, 0.0);

  // use of cos() function for complex number
  cout << "The cos of " << complexnumber << " is "
                     << cos(complexnumber) <<endl;

  return 0;
}
```

**Output:**

```cpp
The cos of (1,0) is (0.540302,-0)

```