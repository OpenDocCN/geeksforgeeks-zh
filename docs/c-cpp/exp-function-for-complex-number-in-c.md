# exp()函数用于 C++ 中的复数

> 原文:[https://www . geesforgeks . org/exp-function-for-complex-number-in-c/](https://www.geeksforgeeks.org/exp-function-for-complex-number-in-c/)

复数的 **exp()** 函数在**复数**头文件中定义。该功能是 **exp()** 功能的复杂版本。该函数用于计算复数 z 的基数 **e** 指数，并返回复数 z 的基数-e 指数。

**语法:**

```cpp
template<class T> complex<T> 
       exp (const complex<T>& z );

```

**参数:**该方法取一个代表复数的强制参数 **z** 。

**返回值:**该函数返回复数 z 的**基数-e 指数**

下面的程序说明了 C++ 中的 exp()函数:

**实施例 1:-**

```cpp
// c++ program to demonstrate
// example of exp() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main()
{
    // initializing the complex: (-1.0+0.0i)
    complex<double> complexnumber(-1.0, 0.0);

    // use of exp() function for complex number
    cout << "The exp of "
         << complexnumber
         << " is "
         << exp(complexnumber)
         << endl;

    return 0;
}
```

**Output:**

```cpp
The exp of (-1,0) is (0.367879,0)

```

**实施例 2:-**

```cpp
// c++ program to demonstrate
// example of exp() function.

#include <bits/stdc++.h>
using namespace std;

// driver program
int main()
{
    // initializing the complex: (0.0 + 1.0i)
    complex<double> complexnumber(0.0, 1.0);

    // use of exp() function for complex number
    cout << "The exp of "
         << complexnumber
         << " is "
         << exp(complexnumber)
         << endl;

    return 0;
}
```

**Output:**

```cpp
The exp of (0,1) is (0.540302,0.841471)

```