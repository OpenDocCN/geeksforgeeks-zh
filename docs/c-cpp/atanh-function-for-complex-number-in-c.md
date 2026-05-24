# c++ 中复数的 atanh()函数

> 原文:[https://www . geesforgeks . org/atanh-c 中复数函数/](https://www.geeksforgeeks.org/atanh-function-for-complex-number-in-c/)

复数的 **atanh()** 函数在**复数**头文件中定义。该功能是 **atanh()** 功能的复杂版本。该函数用于计算复数 z 的复圆弧双曲正切值，并返回复数 z 的圆弧双曲正切值。

**语法:**

```cpp
template<class T> complex<T> 
       atanh (const complex<T>& z );

```

**参数:**该方法取一个代表复数的强制参数 **z** 。

**返回值:**该函数返回复数 z 的**圆弧双曲正切**

下面的程序说明了 C++ 中的 atanh()函数:

**实施例 1:-**

```cpp
// c++ program to demonstrate
// example of atanh() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main()
{
    complex<double> complexnumber(2.0, 0.0);

    // use of atanh() function for complex number
    cout << "The atanh of "
         << complexnumber
         << " is "
         << atanh(complexnumber)
         << endl;

    return 0;
}
```

**Output:**

```cpp
The atanh of (2, 0) is (0.549306, 1.5708)

```

**实施例 2:-**

```cpp
// c++ program to demonstrate
// example of atanh() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main()
{
    complex<double> complexnumber(2.0, -0.0);

    // use of atanh() function for complex number
    cout << "The atanh of "
         << complexnumber
         << " is "
         << atanh(complexnumber)
         << endl;

    return 0;
}
```

**Output:**

```cpp
The atanh of (2, -0) is (0.549306, -1.5708)

```