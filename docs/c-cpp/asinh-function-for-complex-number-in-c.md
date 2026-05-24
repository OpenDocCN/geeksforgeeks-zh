# c++ 中复数的 asinh()函数

> 原文:[https://www . geeksforgeeks . org/asinh-function for-complex-number-in-c/](https://www.geeksforgeeks.org/asinh-function-for-complex-number-in-c/)

复数的 **asinh()** 函数在**复数**头文件中定义。该功能是 **asinh()** 功能的复杂版本。该函数用于计算复数 z 的复弧双曲正弦，并返回复数 z 的弧双曲正弦。

**语法:**

```cpp
template<class T> complex<T> 
       asinh (const complex<T>& z );

```

**参数:**该方法取一个代表复数的强制参数 **z** 。

**返回值:**此函数返回复数 z 的圆弧双曲正弦。

下面的程序说明了 C++ 中的 asinh()函数:

**例 1:**

```cpp
// c++ program to demonstrate
// example of asinh() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main()
{
    complex<double> complexnumber(-2.0, 0.0);

    // use of asinh() function for complex number
    cout << "The asinh of "
         << complexnumber
         << " is "
         << asinh(complexnumber)
         << endl;

    return 0;
}
```

**Output:**

```cpp
The asinh of (-2,0) is (-1.44364,0)

```

**实施例 2:-**

```cpp
// c++ program to demonstrate
// example of asinh() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main()
{
    complex<double> complexnumber(-0.0, -2.0);

    // use of asinh() function for complex number
    cout << "The asinh of "
         << complexnumber
         << " is "
         << asinh(complexnumber)
         << endl;

    return 0;
}
```

**Output:**

```cpp
The asinh of (-0,-2) is (-1.31696,-1.5708)

```