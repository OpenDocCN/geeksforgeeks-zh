# std::cbrt()在 C++ 中

> 原文:[https://www.geeksforgeeks.org/stdcbrt-in-c/](https://www.geeksforgeeks.org/stdcbrt-in-c/)

**std::cbrt()** 是 C++ STL 中的一个内置函数，用来计算数字的立方根。它接受一个数字作为参数，并返回该数字的立方根。
**语法:**

```cpp
// Returns cube root num (num can be
// of type int, double, long double or
// long long type.
// The return type is same as parameter
// passed.
cbrt(num)
```

**参数:**参数可以是 int、double、long double 或 long long 类型。
T3】返回值:返回数字 *num* 的立方根。返回的立方根的数据类型与传递的参数的数据类型相同，除非整数作为参数传递。如果传递的参数是整数，那么 cbrt()函数将返回一个类型为 *double* 的值。
示例:

```cpp
Input : 8
Output : 2 

Input : 9
Output : 2.08008
```

下面程序说明 cbrt()函数:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate the cbrt()
// STL function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // cbrt() function with integral
    // argument
    int num1 = 9;
    cout << cbrt(num1) << endl;

    // cbrt() function with floating-point
    // argumetnt
    double num2 = 7.11;
    cout << cbrt(num2) << endl;

    long long num3 = 7;
    cout << cbrt(num3);

    return 0;
}
```

**输出:**

```cpp
2.08008
1.9229
1.91293
```