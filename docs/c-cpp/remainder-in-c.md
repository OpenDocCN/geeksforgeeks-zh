# c++ 中的余数()

> 原文:[https://www.geeksforgeeks.org/remainder-in-c/](https://www.geeksforgeeks.org/remainder-in-c/)

该函数还用于返回其参数中提到的 2 个浮点数的余数(模)。计算出的商是四舍五入的。
**余数=数–rquot *分母**
其中 rquot 是:数/分母的结果，四舍五入到最接近的整数值(中间的情况四舍五入到偶数)。

**语法:**

```cpp
double remainder(double a, double b)
float remainder(float a, float b)
long double remainder(long double a, long double b)
Parameter:
a and b are the values 
of numerator and denominator.

Return:
The remainder() function returns the floating 
point remainder of numerator/denominator 
rounded to nearest.
```

**错误或异常:**必须给出两个参数，否则会给出错误–**像这样调用“余数()”**没有匹配函数。
**#代码 1**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate
// remainder() function
#include <cmath>
#include <iostream>

using namespace std;

int main()
{
    double a, b;
    double answer;

    a = 50.35;
    b = -4.1;

    // here quotient is -12.2805 and rounded to nearest value then
    // rquot = -12.
    // remainder = 50.35 – (-12 * -4.1)
    answer = remainder(a, b);

    cout << "Remainder of " << a << "/" << b << " is " << answer << endl;

    a = 16.80;
    b = 3.5;

    // here quotient is 4.8 and rounded to nearest value then
    // rquot = -5.
    // remainder = 16.80 – (5 * 3.5)
    answer = remainder(a, b);

    cout << "Remainder of " << a << "/" << b << " is " << answer << endl;

    a = 16.80;
    b = 0;
    answer = remainder(a, b);
    cout << "Remainder of " << a << "/" << b << " is " << answer << endl;

    return 0;
}
```

**输出:**

```cpp
Remainder of 50.35/-4.1 is 1.15
Remainder of 16.8/3.5 is -0.7
Remainder of 16.8/0 is -nan
```

**#代码 2**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate
// remainder() function
#include <cmath>
#include <iostream>

using namespace std;

int main()
{
    int a = 50;
    double b = 41.35, answer;

    answer = remainder(a, b);
    cout << "Remainder of " << a << "/" << b << " = " << answer << endl;

    return 0;
}
```

**输出:**

```cpp
Remainder of 50/41.35 = 8.65 
```