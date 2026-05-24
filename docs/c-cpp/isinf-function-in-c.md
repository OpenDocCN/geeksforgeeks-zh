# isinf()函数在 C++ 中

> 原文:[https://www.geeksforgeeks.org/isinf-function-in-c/](https://www.geeksforgeeks.org/isinf-function-in-c/)

该功能在 **< cmath.h >** 中定义。 **isinf()** 函数用于确定给定的数字是否为无穷大，即正无穷大或负无穷大。如果给定的数字是无穷大，这个函数返回 1，否则这个函数返回 0。

**语法:**

```cpp
bool isinf( float arg );
```

**或**T0

**或**

```cpp
bool isinf( long double arg );
```

**参数:**该函数取一个代表给定浮点值的强制参数 **x** 。

**返回:**如果给定的数字是无穷大，则该函数返回 **1** ，否则返回**0**。

下面的程序说明了 C++ 中的 isinf()函数:

**示例 1:-** 显示返回 1

```cpp
// c++ program to demonstrate
// example of isnormal() function.

#include <bits/stdc++.h>

using namespace std;

int main()
{

    float f = 6.0F;

    // check for +ve infinite value
    cout << "isinf(6.0/0.0) is = " << isinf(f/0.0) << endl;

    // check for -ve infinite value
    f = -1.2F;
    cout << "isinf(-1.2/0.0) is = " << isinf(f/0.0) << endl;

    return 0;
}
```

**的无限情况输出:**

```cpp
isinf(6.0/0.0) is = 1
isinf(-1.2/0.0) is = 1

```

**解释:**在示例 1 中，浮点数表示无穷大，这就是函数返回 1 的原因。

**示例 2:-** 显示返回 0 的非无限情况

```cpp
// c++ program to demonstrate
// example of isinf() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
   cout << "isinf(0.0) is = " << isinf(0.0) << endl;

   cout << "isinf(sqrt(-1.0)) is = " << isinf(sqrt(-1.0)) << endl;

   return 0;
}
```

**输出:**

```cpp
isinf(0.0) is = 0
isinf(sqrt(-1.0)) is = 0

```

**异常:**在示例 2 中，给定的浮点数并不表示无穷大，这就是函数返回 0 的原因。