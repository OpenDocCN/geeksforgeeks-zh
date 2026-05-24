# c++ 17 中的 std::legendre、STD::Legendre 和 STD::Legendre 函数

> 原文:[https://www . geeksforgeeks . org/stdlegendre-stdlegendre-and-stdlegendre-functions-in-c17/](https://www.geeksforgeeks.org/stdlegendre-stdlegendref-and-stdlegendrel-functions-in-c17/)

勒让德、勒让德和勒让德是 C++ STL 中的内置函数，用于计算 n 次和参数 x 的无关联多项式的值。x 的 n 阶无关联[勒让德多项式](https://en.wikipedia.org/wiki/Legendre_polynomials)的值由下式给出:

![  \[         \ P_{n}(x)= \frac{1}{2^{n}n!}\frac{d^{n}}{dx^{n}}(x^{2}-1)^{n}      \]  ](img/ed92d94b1e3513b5d41d97436f023940.png "Rendered by QuickLaTeX.com")

前几个勒让德多项式是

![  \[      Legendre(0,x)= 1 \]  \[      Legendre(1,x)= x \]  \[      Legendre(2,x)= \frac{1}{2} ( 3x^{2}-1 ) \] \[      Legendre(3,x)= \frac{1}{2} ( 5x^{3}-3x ) \] ](img/a62a8a5a945f879dec2bd9e68bf3ad53.png "Rendered by QuickLaTeX.com")

**语法:**

```cpp
double legendre( unsigned int n, double x )
             or 
double legendre( unsigned int n, float x )
             or 
double legendre( unsigned int n, long double x )
             or
float legendref( unsigned int n, float x )
             or
long double legendrel( unsigned int n, long double x )

```

**参数**:该功能接受两个强制参数，描述如下:

*   **n:** 指定多项式的次数。
*   **x:** 它指定表示浮点型或整型值的参数

**返回值:**函数返回参数 x 的 n 阶无关联勒让德多项式的值，返回类型取决于传递的参数。

**注**:函数运行在 C++ 17(7.1)及以上版本。

下面的程序说明了上述功能:

```cpp
// C++ program to illustrate the above 
// mentioned three functions
#include <cmath> 
#include <iostream>
using namespace std;
int main()
{
    // int and double as parameter 
    cout << "legendre(2,0.3)= " << legendre(2,0.3);

    //  x as double type parameter
    cout << "\nlegendre(3,(double)0.4)=" << legendre(3,(double)0.4);

     // x as float 
     cout << "\nlegendre(3,(float)0.4)= " << legendre(3,(float)0.4);

    //  legendref 
    cout << "\nlegendref(3, 0.45)= " << legendref(3, 0.45);

    // legendrel
    cout << "\nlegendrel(7, 0.50)= " << legendrel(7, 0.50);

    return 0;
}
```

**错误和异常**:该函数在以下三种情况下抛出错误:

*   如果参数是 **NaN，则返回** NaN，并且不报告域错误
*   不需要为|x|>1 定义函数
*   如果 n 大于或等于 128，则行为是实现定义的

以下程序说明了上述错误:

**程序 1:**

```cpp
// C++ program to illustrate the above 
// mentioned three functions
// domain error
#include <cmath> 
#include <iostream>
using namespace std;
int main()
{
    // int and double as parameter 
    cout << "legendre(129, 2)= " << legendre(129, 2);

    return 0;
}
```

**输出:**

```cpp
terminate called after throwing an instance of 'std::domain_error'
  what():  Argument out of range in __poly_legendre_p.
legendre(129, 2)=

```

**程序 2:**

```cpp
// C++ program to illustrate the above 
// mentioned three functions
// when x is NaN
#include <cmath> 
#include <iostream>
using namespace std;
int main()
{
    // int and double as parameter 
    cout << "legendre(129, NaN)= " << legendre(129, sqrt(-2));

    return 0;
}
```

**输出:**

```cpp
legendre(129, NaN)= nan

```

**程序 3:**

```cpp
// C++ program to illustrate the above 
// mentioned three functions
// domain error
#include <cmath> 
#include <iostream>
using namespace std;
int main()
{
    // int and double as parameter 
    cout << "legendre(129, 2)= " << legendre(129, 2);

    return 0;
}
```

**输出:**

```cpp
terminate called after throwing an instance of 'std::domain_error'
  what():  Argument out of range in __poly_legendre_p.

```