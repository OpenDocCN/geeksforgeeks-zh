# c++ 中复数的 atan()函数

> 原文:[https://www . geesforgeks . org/atan-c 中复数的函数/](https://www.geeksforgeeks.org/atan-function-for-complex-number-in-c/)

复数的 **atan()** 函数在**复数**头文件中定义。该功能是 **atan()** 功能的复杂版本。该函数用于计算复数 z 的复反正切，并返回复数 z 的反正切。

**语法:**

```cpp
template<class T> complex<T> 
       atan (const complex<T>& z );

```

**参数:**该方法取一个代表复数的强制参数 **z** 。

**返回值:**该函数返回复数 z 的**反正切**

下面的程序说明了 C++ 中的 atan()函数:

**实施例 1:-**

```cpp
// c++ program to demonstrate
// example of atan() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main()
{
    complex<double> complexnumber(-2.0, 0.0);

    // use of atan() function for complex number
    cout << "The atan of "
         << complexnumber
         << " is "
         << atan(complexnumber)
         << endl;

    return 0;
}
```

**Output:**

```cpp
The atan of (-2,0) is (-1.10715,0)

```

**实施例 2:-**

```cpp
// c++ program to demonstrate
// example of atan() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main()
{
    complex<double> complexnumber(0.0, 2.0);

    // use of atan() function for complex number
    cout << "The atan of "
         << complexnumber
         << " is "
         << atan(complexnumber)
         << endl;

    return 0;
}
```

**Output:**

```cpp
The atan of (0,2) is (1.5708,0.549306)

```