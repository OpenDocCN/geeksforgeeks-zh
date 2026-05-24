# c++ 中的 fma()函数

> 原文:[https://www.geeksforgeeks.org/fma-function-in-c/](https://www.geeksforgeeks.org/fma-function-in-c/)

**fma()** 函数接受三个参数 a、b 和 c，并在不损失精度的情况下返回 a*b+c。fma()函数在 **cmath** 头文件中定义。
如果传递给 **fma()** 的任何参数是长双精度，返回类型是长双精度。如果不是，返回类型是 double。

**语法:**

```cpp
double fma(double a, double b, double c);

or,
long double fma(long double a, long double b, long double c);

or,
float fma(float a, float b, float c)

```

**参数:**该函数取三个参数。

*   **a** :第一个要相乘的参数。
*   **b** :要与 a 相乘的第二个参数
*   **c** :要加到 a 和 b 乘积上的第三个自变量。

**返回:**fma()函数返回*b+c。

下面的程序说明了 C++ 中的 fma()函数:

**程序 1:**

```cpp
// C++ program to demonstrate
// the fma() function

#include<bits/stdc++.h>

using namespace std;

int main()
{
    double a = 3.4, b = 2.1, c = 4.2;
    double ans = fma(a, b, c);

    cout << "fma(a, b, c)= " << ans << endl;

    return 0;
}
```

**Output:**

```cpp
fma(a, b, c)= 11.34

```

**程序 2:**

```cpp
// CPP program to demonstrate
// fma() function

#include<bits/stdc++.h>
using namespace std;

int main()
{
    double b = 2.1, c = 4.2;
    long double lda = 9.4, answer;

    answer = fma(lda, c, b);

    cout << "fma(lda, c, b)=" << answer << endl;

    return 0;
}
```

**Output:**

```cpp
fma(lda, c, b)=41.58

```