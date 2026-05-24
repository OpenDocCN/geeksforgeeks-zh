# c++ 中复数的幂()函数

> 原文:[https://www . geesforgeks . org/power-function-for-complex-number-in-c/](https://www.geeksforgeeks.org/pow-function-for-complex-number-in-c/)

复数的 **pow()** 函数在**复数**头文件中定义。该功能是 **pow()** 功能的复杂版本。这个函数用来计算 x 的复数幂次升到 y 次方。

**语法:**

> **模板<类 T >复数< T >幂(const 复数<T>T8】x，int y)；**
> 
> 或者，
> **模板<类 T >复< T >幂(const 复<T>T9】x，const 复<T>T12】y)；**
> 
> 或者，
> **模板<类 T >复< T >幂(const 复<T>T9】x，const T&y)；**
> 
> 或者，
> **模板<类 T >复< T >幂(const T & x，const 复<T>T10】y)；**

**参数:**该方法接受两个参数:

*   **x:** 表示基数为复数。
*   **y:** 表示指数为复数值。

**返回值:**此函数返回 x 基数的**复幂**升至 y 次方。

下面的程序说明了 C++ 中的 pow()函数:

**实施例 1:-**

```cpp
// c++ program to demonstrate
// example of pow() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main()
{
    // initializing the complex: (1.0+2.0i)
    complex<double> complexnumber(1.0, 2.0);

    // use of pow() function for complex number
    cout << "(1.0, 2.0)^2 = "
         << pow(complexnumber, 2)
         << endl;

    return 0;
}
```

**Output:**

```cpp
(1.0, 2.0)^2 = (-3,4)

```

**实施例 2:-**

```cpp
// c++ program to demonstrate
// example of pow() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main()
{
    // initializing the complex: (2.0+1.0i)
    complex<double> complexnumber(2.0, 1.0);

    // use of pow() function for complex number
    cout << "(2.0, 1.0)^3 = "
         << pow(complexnumber, 3)
         << endl;

    return 0;
}
```

**Output:**

```cpp
(2.0, 1.0)^3 = (2,11)

```