# c++ 中的 frexp()

> 原文:[https://www.geeksforgeeks.org/frexp-in-c/](https://www.geeksforgeeks.org/frexp-in-c/)

函数的作用是:将浮点数 x 分解成二进制的有效数，即绝对值在[0.5，1.0]之间的浮点数，整数指数为 2。

**x =有效数* (2^exponent).** 
**它曾经:**

```cpp
1\. It is used to find significand which is always between 0.5 and 1.0
2\. It is used to find exponent which is power of 2.

```

**语法:**

```cpp
double frexp (double x);
float frexp (float x);
long double frexp (long double x);

```

> **参数:**
> 
> *   frexp()函数接受一个参数。
>     
>     **返回:**
>     
>     
> *   The function returns the binary significant number whose absolute value is in the interval [0.5,1].
> *   If x is zero, the significant number and exponent are both zero.

**错误和异常:**

1.  必须给出这两个参数，否则会给出错误**调用“frexp()”**没有匹配的函数。
2.  如果我们传递一个字符串作为参数，我们将得到一个错误，没有匹配的函数调用' frexp(const char [n])。

**#代码 1**

```cpp
// CPP implementation of 
// above function
#include <cmath>
#include <iostream>

using namespace std;

// Driver program
int main()
{
    double x = 5.35, significand;
    int exponent;
    significand = frexp(x, &exponent);
    cout << x << " = " << significand 
         << " * 2^" << exponent << endl;

    return 0;
}
```

**Output:**

```cpp
5.35 = 0.66875 * 2^3

```

**#代码 2**

```cpp
// CPP implementation of the 
// above function
#include <cmath>
#include <iostream>

using namespace std;

// Driver program
int main()
{
    double significand;
    int exponent, x = 5;
    significand = frexp(x, &exponent);
    cout << x << " = " << significand 
         << " * 2^" << exponent << endl;

    return 0;
}
```

**Output:**

```cpp
5 = 0.625 * 2^3

```