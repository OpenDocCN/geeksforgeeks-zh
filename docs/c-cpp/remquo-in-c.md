# c++ 中的 remquo()

> 原文:[https://www.geeksforgeeks.org/remquo-in-c/](https://www.geeksforgeeks.org/remquo-in-c/)

该函数用于返回其参数中提到的 2 个浮点数的余数(模)，并存储传递给它的指针的商。计算出的商是四舍五入的。

余数=数–rquot * denom
其中 rquot 是:分子/分母的结果，向最近的整数值舍入(中间情况向偶数舍入)。

**语法:**

```cpp
long double remquo(long double a, long double b, int* q);
double remquo(double a, double b, int* q);
float remquo(float a, float b, int* q);

```

> **参数:**
> 
> *   **a** and **b** are the values of numerator and denominator. **q** is the pointer in which quotient will be stored.
>     
>     **返回:**
>     
>     *   它返回四舍五入到最近的分子/分母的浮点余数，并将商存储在 q 中。

**错误:**

2.  必须给出所有三个参数，否则会给出错误**没有匹配函数调用“rem quo”**。
3.  It is mandatory to pass third argument a pointer because it stores address of quotient otherwise it will give error **‘remquo(double&, double&, int&)’**

    。

**示例:**

```cpp
Input : remquo(12.5, 2.2, &q)
Output : -0.7 and q=6

```

**说明:**

```cpp
Input : remquo(-12.5, 2.2, &q)
Output : 0.7 and q=-6

```

**#代码 1**

```cpp
// CPP implementation of the above 
// function
#include <cmath>
#include <iostream>

using namespace std;

int main()
{
    int q;
    double a = 12.5, b = 2.2;

    // it will return remainder 
    // and stores quotient in q
    double answer = remquo(a, b, &q);

    cout << "Remainder of " << a << "/" 
         << b << " is " << answer << endl;

    cout << "Quotient of " << a << "/" 
         << b << " is " << q << endl
         << endl;

    a = -12.5;

    // it will return remainder 
    // and stores quotient in q
    answer = remquo(a, b, &q);

    cout << "Remainder of " << a << "/" << b 
         << " is " << answer << endl;

    cout << "Quotient of " << a << "/" << b 
         << " is " << q << endl
         << endl;

    b = 0;

    // it will return remainder
    // and stores quotient in q
    answer = remquo(a, b, &q);

    cout << "Remainder of " << a << "/" << b 
         << " is " << answer << endl;

    cout << "Quotient of " << a << "/" << b 
         << " is " << q << endl
         << endl;

    return 0;
}
```

**输出:**

```cpp
Remainder of 12.5/2.2 is -0.7
Quotient of 12.5/2.2 is 6

Remainder of -12.5/2.2 is 0.7
Quotient of -12.5/2.2 is -6

Remainder of -12.5/0 is -nan
Quotient of -12.5/0 is -6

```

**#代码 2**

```cpp
// CPP implementation of the
// above function
#include <cmath>
#include <iostream>

using namespace std;

int main()
{
    int q;
    double a = 12.5;
    int b = 2;

    // it will return remainder
    // and stores quotient in q
    double answer = remquo(a, b, &q);

    cout << "Remainder of " << a << "/" << b 
         << " is " << answer << endl;

    cout << "Quotient of " << a << "/" << b 
         << " is " << q << endl
         << endl;

    return 0;
}
```

**输出:**

```cpp
Remainder of 12.5/2 is 0.5
Quotient of 12.5/2 is 6

```