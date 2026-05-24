# C++ 数学函数

> 原文:[https://www.geeksforgeeks.org/c-mathematical-functions/](https://www.geeksforgeeks.org/c-mathematical-functions/)

C++ 是 C 的超集，支持大量有用的数学函数。这些函数在标准 C++ 和 C 中可用，以支持各种数学计算。这些函数可以直接用于简化代码和程序，而不是专注于实现。C++ 提供了大量的数学函数，如下所述–
为了使用这些函数，您需要包含头文件- **< math.h >** 或 **< cmath >** 。

1.  **双正弦(double)** :该函数以角度(以度为单位)为自变量，返回其正弦值，可以使用正弦曲线进行验证。
2.  **double cos(double)** :该函数以角度(以度为单位)为自变量，返回其余弦值，可以使用余弦曲线进行验证。
3.  **双 tan(double)** :此函数以角度(以度为单位)为自变量，返回其正切值。这也可以用三角法来验证，如 Tan(x) = Sin(x)/Cos(x)。
4.  **double sqrt(double)** :此函数以数字为自变量，返回其平方根值。数字不能为负值。
5.  **int abs(int)** :此函数以整数为自变量，返回其绝对值。这意味着，不管输入的符号是什么，输出总是正的。
6.  **双次幂(double，double)** :此函数以一个自变量为基数，另一个为指数。
7.  **双海波(double，double)** :该功能要求直角三角形的两条边作为其斜边给出输出。
8.  **双层(双层)**:此函数返回小于或等于函数中传递的参数的整数值。
9.  **双晶圆厂(double)** :此函数返回任意数字的绝对值。
10.  **double acos(double)** :此函数返回自变量的弧余弦。acos()的参数必须在-1 到 1 的范围内；否则，会出现域错误。
11.  **double asin(double)** :此函数返回自变量的反正弦。asin()的参数必须在-1 到 1 的范围内；否则，会出现域错误。
12.  **double atan(double)** :此函数返回 arg 的反正切。
13.  **double atan2(double，double)** :此函数返回(double a)/(double b)的反正切。
14.  **double ceil(double)** :此函数返回最小整数为 double，不小于提供的参数。
15.  **double cosh(double)** :这个函数返回提供的自变量的双曲余弦。提供的参数值必须以弧度为单位。
16.  **double tanh(double)** :此函数返回所提供参数的双曲正切值。提供的参数值必须以弧度为单位。
17.  **双对数(double)** :该函数取一个数，返回该数的自然对数。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate some of the
// above mentioned functions

#include <iostream>
#include <math.h>
using namespace std;

int main()
{
    double x = 2.3;
    cout << "Sine value of x=2.3 : " << sin(x) << endl;
    cout << "Cosine value of x=2.3 : " << cos(x) << endl;
    cout << "Tangent value of x=2.3 : " << tan(x) << endl;

    double y = 0.25;
    cout << "Square root value of y=0.25 : " << sqrt(y) << endl;

    int z = -10;
    cout << "Absolute value of z=-10 : " << abs(z) << endl;
    cout << "Power value: x^y = (2.3^0.25) : " << pow(x, y) << endl;

    x = 3.0;
    y = 4.0;
    cout << "Hypotenuse having other two sides as x=3.0 and"
         << " y=4.0 : " << hypot(x, y) << endl;

    x = 4.56;
    cout << "Floor value of x=4.56 is : " << floor(x) << endl;

    x = -4.57;
    cout << "Absolute value of x=-4.57 is : " << fabs(x) << endl;

    x = 1.0;
    cout << "Arc Cosine value of x=1.0 : " << acos(x) << endl;
    cout << "Arc Sine value of x=1.0 : " << asin(x) << endl;
    cout << "Arc Tangent value of x=1.0 : " << atan(x) << endl;

    y = 12.3;
    cout << "Ceiling value of y=12.3 : " << ceil(y) << endl;

    x = 57.3; // in degrees
    cout << "Hyperbolic Cosine of x=57.3 : " << cosh(x) << endl;
    cout << "Hyperbolic tangent of x=57.3 : " << tanh(x) << endl;

    y = 100.0;
    // Natural base with 'e'
    cout << "Log value of y=100.0 is : " << log(y) << endl;

    return 0;
}
```

**Output:** 

```cpp
Sine value of x=2.3 : 0.745705
Cosine value of x=2.3 : -0.666276
Tangent value of x=2.3 : -1.11921
Square root value of y=0.25 : 0.5
Absolute value of z=-10 : 10
Power value: x^y = (2.3^0.25) : 1.23149
Hypotenuse having other two sides as x=3.0 and y=4.0 : 5
Floor value of x=4.56 is : 4
Absolute value of x=-4.57 is : 4.57
Arc Cosine value of x=1.0 : 0
Arc Sine value of x=1.0 : 1.5708
Arc Tangent value of x=1.0 : 0.785398
Ceiling value of y=12.3 : 13
Hyperbolic Cosine of x=57.3 : 3.83746e+24
Hyperbolic tangent of x=57.3 : 1
Log value of y=100.0 is : 4.60517
```