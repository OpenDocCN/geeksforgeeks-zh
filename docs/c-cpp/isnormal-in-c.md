# 在 C++ 中是正常的()

> 原文:[https://www.geeksforgeeks.org/isnormal-in-c/](https://www.geeksforgeeks.org/isnormal-in-c/)

该功能在 **< cmath.h >** 中定义。通过使用 **isnormal()** 函数，我们确定给定的数是否正常(既不是零，也不是无穷大，也不是 NAN)。如果数字正常，此函数返回 1，否则返回 0。

**语法:**

```cpp
bool  isnormal(float x);
```

**或**

```cpp
bool  isnormal(double x); 
```

**或**

```cpp
bool  isnormal(long double x); 
```

**参数:**该函数取一个代表浮点值的强制参数 **x** 。

**返回:**如果给定值正常，则函数返回 **1** 否则函数返回**0**。

下面的程序说明了 C++ 中的 isnormal()函数:

**示例 1:-** 用浮点值显示

```cpp
// c++ program to demonstrate
// example of isnormal() function.

#include <bits/stdc++.h>

using namespace std;

int main()
{

    float f = 7.0F;

    // check for non-zero value
    cout << "isnormal(7.0) is = " << isnormal(f) << endl;

    // check for zero
    f = 0.0F;
    cout << "isnormal(0.0) is = " << isnormal(f) << endl;

    // check for infinite value
    f = 9.2F;
    cout << "isnormal(9.2/0.0) is = " << isnormal(f / 0.0) << endl;

    return 0;
}
```

**Output:**

```cpp
isnormal(7.0) is = 1
isnormal(0.0) is = 0
isnormal(9.2/0.0) is = 0

```

**例 2:-** 用双值显示

```cpp
// c++ program to demonstrate
// example of isnormal() function.

#include <bits/stdc++.h>

using namespace std;

int main()
{

    double f = 7.0;

    // check for non-zero value
    cout << "isnormal(7.0) is = " << isnormal(f) << endl;

    // check for zero
    f = 0.0;
    cout << "isnormal(0.0) is = " << isnormal(f) << endl;

    // check for infinite value
    f = 9.2;
    cout << "isnormal(9.2/0.0) is = " << isnormal(f / 0.0) << endl;

    return 0;
}
```

**Output:**

```cpp
isnormal(7.0) is = 1
isnormal(0.0) is = 0
isnormal(9.2/0.0) is = 0

```

**例 3:-** 用长双数值显示

```cpp
// c++ program to demonstrate
// example of isnormal() function.

#include <bits/stdc++.h>

using namespace std;

int main()
{

    long double f = 7.0;

    // check for non-zero value
    cout << "isnormal(7.0) is = " << isnormal(f) << endl;

    // check for zero
    f = 0.0;
    cout << "isnormal(0.0) is = " << isnormal(f) << endl;

    // check for infinite value
    f = 9.2;
    cout << "isnormal(9.2/0.0) is = " << isnormal(f / 0.0) << endl;

    return 0;
}
```

**Output:**

```cpp
isnormal(7.0) is = 1
isnormal(0.0) is = 0
isnormal(9.2/0.0) is = 0

```