# tan()函数为 C++ 中的复数

> 原文:[https://www . geesforgeks . org/tan-function-for-complex-number-in-CPP/](https://www.geeksforgeeks.org/tan-function-for-complex-number-in-cpp/)

复数的 **tan()** 函数在**复数**头文件中定义。该功能是 **tan()** 功能的复杂版本。此函数用于计算复数 z 的复数 tan，此函数返回复数 z 的 tan。

**语法:**

```cpp
tan(z);
```

**参数:**

*   **z:** 该方法取一个代表复数的强制参数 **z** 。

**返回值:**这个函数返回复数 z 的 tan()。
下面的程序说明了 C++ 中的 tan()函数:
T4【程序 1:-

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// example of tan() function.
#include <iostream>
#include <complex>
using namespace std;

int main ()
{
  complex<double> complexnumber (0.0, 1.0);

  // use of tan() function for complex number
  cout << "The tan of " << complexnumber << " is "
                     << tan(complexnumber) <<endl;

  return 0;
}
```

**Output:** 

```cpp
The tan of (0,1) is (0,0.761594)
```

**程序 2:-**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// example of tan() function.
#include <iostream>
#include <complex>
using namespace std;

int main ()
{
  complex<double> complexnumber (1.0, 0.0);

  // use of tan() function for complex number
  cout << "The tan of " << complexnumber << " is "
                     << tan(complexnumber) << endl;

  return 0;
}
```

**Output:** 

```cpp
The tan of (1,0) is (1.55741,0)
```