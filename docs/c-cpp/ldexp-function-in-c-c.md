# C/c++

中的 ldexp()函数

> 原文:[https://www.geeksforgeeks.org/ldexp-function-in-c-c/](https://www.geeksforgeeks.org/ldexp-function-in-c-c/)

**ldexp()** 是 C/C++ 中的一个内置函数，通过取两个参数 x 和 exp，即 ***x * 2^exp*** ，给出任意变量 x 和 2 的乘积乘以 exp 的幂

**语法:**

```cpp
float ldexp (float x, int exp)
double ldexp (double x, int exp)
long double ldexp (long double x, int exp)
double ldexp (T x, int exp)

```

**参数:**函数接受两个强制参数 **x** 和 **exp** ，指定定义中描述的两个变量。

**返回值:**函数返回表达式 ***x * 2^exp*** 的值。它返回 long double、float 或 double 类型的值。

下面的程序说明了上面的功能。

**程序 1:**

```cpp
// C++ program to illustrate the
// ldexp() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    double x = 6, result;
    int exp = 2;

    // It returns x*(2^exp)
    result = ldexp(x, exp);

    // print the result
    cout << "ldexp(x, exp) = " << result << endl;
    return 0;
}
```

**Output:**

```cpp
ldexp(x, exp) = 24

```

**程序 2:**

```cpp
// C++ program to illustrate the
// ldexp() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    double result;
    int x = 20, exp = 9;
    // It returns x*(2^exp)
    result = ldexp(x, exp);

    // prints the result
    cout << "ldexp(x, exp) = " << result << endl;
    return 0;
}
```

**Output:**

```cpp
ldexp(x, exp) = 10240

```

**错误和异常:**如果结果的幅度太大，无法用返回类型的值来表示，则函数返回带有适当符号的**巨 _ 瓦尔**(或巨 _ 瓦尔或巨 _VALL)，并出现*溢出范围错误*。

下面的程序说明了上面的错误。

```cpp
// C++ program to illustrate the
// ldexp() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    double result;
    int x = 20, exp = 10000;

    // It returns x*(2^exp)
    result = ldexp(x, exp);

    // prints the result
    cout << "ldexp(x, exp) = " << result << endl;
    return 0;
}
```

**Output:**

```cpp
ldexp(x, exp) = inf

```