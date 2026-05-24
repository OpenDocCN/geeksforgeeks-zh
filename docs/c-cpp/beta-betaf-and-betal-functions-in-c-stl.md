# β()，βf()和βl()函数在 C++ STL 中

> 原文:[https://www . geesforgeks . org/beta-beta f-和-betal-functions-in-c-stl/](https://www.geeksforgeeks.org/beta-betaf-and-betal-functions-in-c-stl/)

**β()，βf()和βl()**是 C++ STL 中的内置函数，用于计算两个正实数值的[β函数](https://en.wikipedia.org/wiki/Beta_function)。该函数以两个变量 x 和 y 为输入，返回 x 和 y 的β函数。x 和 y 的β函数(也称为第一类欧拉积分)可以定义为:

![$B(x, y)=\int_0^1 t^{x-1} (1-t)^{y-1} dt $ ](img/20e1fd3b01cac62159eeefda5cad4833.png "Rendered by QuickLaTeX.com")

**语法**

```cpp
double beta(double x, double y)
or 
long double betal(long double x, long double y)
or 
float betaf(float x, float y)
```

**参数:**该函数接受两个强制参数 x 和 y，这两个参数指定浮点或整数类型的值。参数可以是 double、double 或 float、float 或 long double、long double 数据类型。
**返回值:**函数返回 x 和 y 的 beta 函数值，返回类型取决于传递的参数。它与参数的相同。
**注**:函数运行于 **C++ 17(7.1)及以上。**
下面的程序说明了 beta()、betaf()和 betal()的功能:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the three functions
// Being a special function, beta is only guaranteed
// to be in cmath if the user defines
//  __STDCPP_WANT_MATH_SPEC_FUNCS__ before including
// any standard library headers.
#define __STDCPP_WANT_MATH_SPEC_FUNCS__ 1
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Computes the beta function of 5 and 4 and print it
    // If provided arguments are not of type double
    // they are implicitly type-casted to the higher type.

    // first example of beta()
    cout << beta(5, 4) << "\n";

    // second example of betaf()
    cout << betaf(10.0, 4.0) << "\n";

    // third example of betal()
    cout << betal(10.0, 6.7) << "\n";
    return 0;
}
```

**输出:**

```cpp
0.00357143
0.00034965
1.65804e-005
```

**β函数的应用:**用于计算二项式系数。根据β函数，二项式系数可以表示为:

![$\binom{n}{k}= \frac{1}{(n+1)B(n-k+1, k+1)}$ ](img/f7d32b3692a5e02b2f29f3eea35051a8.png "Rendered by QuickLaTeX.com")

上述关系可用于计算二项式系数。图示如下:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to print the pascal triangle
// Being a special function, beta is only guaranteed
// to be in cmath if the user defines
//  __STDCPP_WANT_MATH_SPEC_FUNCS__ before including
// any standard library headers.
#define __STDCPP_WANT_MATH_SPEC_FUNCS__ 1
#include <bits/stdc++.h>
#include <cmath>
using namespace std;

// Function to return the value of binomial Coefficient
double binomialCoefficient(int n, int k)
{
    // Calculate the value of nCr using above formula.
    double ans = 1 / ((n + 1) * beta(n - k + 1, k + 1));
    return ans;
}
// Driver Code
int main()
{
    // Print the binomial Coefficient nCr where n=5 and r=2
    cout << binomialCoefficient(5, 2) << "\n";

    return 0;
}
```

**输出:**

```cpp
10
```