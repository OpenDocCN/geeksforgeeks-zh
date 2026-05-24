# c++ 中复数的 asin()函数

> 原文:[https://www . geesforgeks . org/asin-function-for-complex-number-in-c/](https://www.geeksforgeeks.org/asin-function-for-complex-number-in-c/)

复数的 **asin()** 函数在**复数**头文件中定义。该功能是 **asin()** 功能的复杂版本。该函数用于计算复数 z 的复反正弦，并返回复数 z 的反正弦。

**语法:**

```cpp
template<class T> complex<T> 
       asin (const complex<T>& z );

```

**参数:**该方法取一个代表复数的强制参数 **z** 。

**返回值:**该函数返回复数 z 的**反正弦**

下面的程序说明了 C++ 中的 asin()函数:

**例 1:**

```cpp
// c++ program to demonstrate
// example of asin() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main()
{
    complex<double> complexnumber(-2.0, 0.0);

    // use of asin() function for complex number
    cout << "The asin of "
         << complexnumber
         << " is "
         << asin(complexnumber)
         << endl;

    return 0;
}
```

**Output:**

```cpp
The asin of (-2,0) is (-1.5708,1.31696)

```

**实施例 2:-**

```cpp
// c++ program to demonstrate
// example of asin() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main()
{
    complex<double> complexnumber(-2.0, -0.0);

    // use of asin() function for complex number
    cout << "The asin of "
         << complexnumber
         << " is "
         << asin(complexnumber)
         << endl;

    return 0;
}
```

**Output:**

```cpp
The asin of (-2,-0) is (-1.5708,-1.31696)

```