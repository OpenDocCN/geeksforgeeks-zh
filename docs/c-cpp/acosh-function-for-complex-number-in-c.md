# c++ 中复数的 acosh()函数

> 原文:[https://www . geesforgeks . org/acosh-function-for-complex-number-in-c/](https://www.geeksforgeeks.org/acosh-function-for-complex-number-in-c/)

复数的 **acosh()** 函数在**复数**头文件中定义。该功能是 **acosh()** 功能的复杂版本。该函数用于计算复数 z 的复弧双曲余弦，并返回复数 z 的弧双曲余弦。

**语法:**

```cpp
template<class T> complex<T> 
       acosh (const complex<T>& z );

```

**参数:**该方法取一个代表复数的强制参数 **z** 。

**返回值:**该函数返回复数 z 的**弧双曲余弦**

下面的程序说明了 C++ 中的 acosh()函数:

**实施例 1:-**

```cpp
// c++ program to demonstrate
// example of acosh() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main()
{
    complex<double> complexnumber(-2.0, 0.0);

    // use of acosh() function for complex number
    cout << "The acosh of "
         << complexnumber
         << " is "
         << acosh(complexnumber)
         << endl;

    return 0;
}
```

**Output:**

```cpp
The acosh of (-2,0) is (1.31696,3.14159)

```

**实施例 2:-**

```cpp
// c++ program to demonstrate
// example of acosh() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main()
{
    complex<double> complexnumber(0.5, 0.0);

    // use of acosh() function for complex number
    cout << "The acosh of "
         << complexnumber
         << " is "
         << acosh(complexnumber)
         << endl;

    return 0;
}
```

**Output:**

```cpp
The acosh of (0.5,0) is (0,1.0472)

```