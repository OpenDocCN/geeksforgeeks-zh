# c++ 中的 real()函数

> 原文:[https://www.geeksforgeeks.org/real-function-in-c/](https://www.geeksforgeeks.org/real-function-in-c/)

**real()** 函数在**复杂的**头文件中定义。实数()函数用来求复数的实数部分。

**语法:**

```cpp
template<class T> T 
    real(const complex<T>& z);

```

**参数:**该方法取一个强制参数 **z:** ，代表给定的复数。

**返回:**返回指定复数的**实部**。

以下程序说明了上述功能

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of real() function.

#include <bits/stdC++.h>
using namespace std;

// driver function
int main()
{
    // defines the complex number: (20.3 + 4.9i)
    complex<double> realpart(20.3, 4.9);

    // print the complex number
    cout << "Complex Number = "
         << realpart << endl;

    // prints the real part using the real function
    cout << "Real part of the complex number is ="
         << real(realpart) << endl;

    return 0;
}
```

**Output:**

```cpp
Complex Number = (20.3, 4.9)
Real part of the complex number is =20.3

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of real() function.

#include <bits/stdC++.h>
using namespace std;

// driver function
int main()
{
    // defines the complex number: (2 + 2i)
    complex<double> realpart(2, 2);

    // print the complex number
    cout << "Complex Number = "
         << realpart << endl;

    // prints the real part using the real function
    cout << "Real part of the complex number is ="
         << real(realpart) << endl;

    return 0;
}
```

**Output:**

```cpp
Complex Number = (2, 2)
Real part of the complex number is =2

```