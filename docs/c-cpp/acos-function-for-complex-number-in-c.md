# c++ 中复数的 acos()函数

> 原文:[https://www . geeksforgeeks . org/acos-function for-complex-number-in-c/](https://www.geeksforgeeks.org/acos-function-for-complex-number-in-c/)

复数的 **acos()** 函数在**复数**头文件中定义。该功能是 **acos()功能**的复杂版本。该函数用于计算复数 z 的复弧余弦，并返回复数 z 的弧余弦。

**语法:**

```cpp
template<class T> complex<T> 
       acos (const complex<T>& z );

```

**参数:**该方法接受一个代表复数的强制参数 **z** 。

**返回值:**该函数返回复数 z 的**弧余弦**

下面的程序说明了 C++ 中的 acos()函数:

**实施例 1:-**

```cpp
// c++ program to demonstrate
// example of acos() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main()
{
    complex<double> complexnumber(-2.0, 0.0);

    // use of acos() function for complex number
    cout << "The acos of "
         << complexnumber
         << " is "
         << acos(complexnumber)
         << endl;

    return 0;
}
```

**Output:**

```cpp
The acos of (-2,0) is (3.14159,-1.31696)

```

**实施例 2:-**

```cpp
// c++ program to demonstrate
// example of acos() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main()
{
    complex<double> complexnumber(-2.0, -0.0);

    // use of acos() function for complex number
    cout << "The acos of "
         << complexnumber
         << " is "
         << acos(complexnumber)
         << endl;

    return 0;
}
```

**Output:**

```cpp
The acos of (-2,-0) is (3.14159,1.31696)

```