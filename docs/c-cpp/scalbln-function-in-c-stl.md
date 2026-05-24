# c++ STL 中的 scalbln()函数

> 原文:[https://www.geeksforgeeks.org/scalbln-function-in-c-stl/](https://www.geeksforgeeks.org/scalbln-function-in-c-stl/)

**scalbln()** 是 C++ STL 中的内置函数，它接受两个参数，并通过将 FLT_RADIX 提升为 n 的幂来缩放 x。该函数返回 x 和 FLT_RADIX 提升为 n 的幂的乘积。

**FLT_RADIX:** 是指数表示的基数(整数基数)的值。

**语法**:

```cpp
scalbln (x, n)
```

**参数**:该功能接受两个强制参数，描述如下:

*   **x**–指定表示有效数的值。数据类型可以是 double、float 或 long-double。
*   **n**–指定 FLT 基数的指数。参数的数据类型为 long-int。

**返回类型**:该函数返回 x 和 FLT_RADIX 的乘积的幂 n，返回值与 x 的数据类型相同

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate
// scalbln() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    long int n = 0;
    double x = 2.12, result;
    result = scalbln(x, n);
    cout << x << " * " << FLT_RADIX << "^" 
    << n << " = " << result << endl;

    return 0;
}
```

**Output:**

```cpp
2.12 * 2^0 = 2.12

```

**程序 2:**

```cpp
// C++ program to illustrate
// scalbln() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    long int n = 9999999;
    double x = 19.8, result;
    result = scalbln(x, n);
    cout << x << " * " << FLT_RADIX << "^" 
    << n << " = " << result << endl;

    return 0;
}
```

**Output:**

```cpp
19.8 * 2^9999999 = inf

```