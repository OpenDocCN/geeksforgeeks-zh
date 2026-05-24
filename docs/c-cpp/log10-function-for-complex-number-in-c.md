# c++ 中复数的 log10()函数

> 原文:[https://www . geesforgeks . org/log 10-c 中复数函数/](https://www.geeksforgeeks.org/log10-function-for-complex-number-in-c/)

复数的 **log10()** 函数在**复数**头文件中定义。该功能是 **log10()** 功能的复杂版本。该函数用于计算复数 z 的复数公共对数，即以 **10** 为基数，返回复数 z 的公共对数。

**语法:**

```cpp
template<class T> complex<T> 
       log10 (const complex<T>& z );

```

**参数:**该方法取一个代表复数的强制参数 **z** 。

**返回值:**该函数返回复数 z 的**常用对数**

下面的程序说明了 C++ 中的 log10()函数:

**实施例 1:-**

```cpp
// c++ program to demonstrate
// example of log10() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main()
{
    // initializing the complex: (-1.0+0.0i)
    complex<double> complexnumber(-1.0, 0.0);

    // use of log10() function for complex number
    cout << "The log10 of "
         << complexnumber
         << " is "
         << log10(complexnumber)
         << endl;

    return 0;
}
```

**Output:**

```cpp
The log10 of (-1,0) is (0,1.36438)

```

**实施例 2:-**

```cpp
// c++ program to demonstrate
// example of log10() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main()
{
    // initializing the complex: (-1.0 + -0.0i)
    complex<double> complexnumber(-1.0, -0.0);

    // use of log10() function for complex number
    cout << "The log10 of "
         << complexnumber
         << " is "
         << log10(complexnumber)
         << endl;

    return 0;
}
```

**Output:**

```cpp
The log10 of (-1,-0) is (0,-1.36438)

```