# c++ 中的 expm 1()

> 原文:[https://www.geeksforgeeks.org/expm1-in-cpp/](https://www.geeksforgeeks.org/expm1-in-cpp/)

expm1(x)函数返回 e<sup>x</sup>–1，其中 x 为自变量，e 为数学常数，值等于 2.71828。

**语法:**

```cpp
double expm1() (double x);
float expm1() (float x);
long double expm1() (long double x);

```

> **参数:**
> 
> *   expm 1()函数接受一个参数并计算 e^x -1。
>     
>     **返回:**
>     
>     
>     
>     
> *   If we pass x in the parameter, the expm1 () function will return e x-1.

**错误和异常:**

2.  必须给出这两个参数，否则会给出错误**调用“expm 1()”**没有匹配的函数。
3.  如果我们将字符串作为参数传递，我们将得到错误**没有匹配的函数来调用‘expm 1(const char[n])**。
4.  如果我们通过**STD::numeric _ limits::max()**我们将得到-2147483648。

**示例:**

```cpp
Input : expm1(5.35)
Output : 209.608

```

```cpp
Input : expm1(-5)
Output : -0.993262

```

**#代码 1**

```cpp
// CPP implementation of the 
// above function
#include <cmath>
#include <iostream>
using namespace std;

int main()
{
    double x = 5.35, answer;
    answer = expm1(x);

    cout << "e^" << x << " - 1 = " 
         << answer << endl;

    return 0;
}
```

**Output:**

```cpp
e^5.35 - 1 = 209.608

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
    int x = -5;
    double answer;
    answer = expm1(x);

    cout << "e^" << x << " - 1 = " 
         << answer << endl;

    return 0;
}
```

**Output:**

```cpp
e^-5 - 1 = -0.993262

```