# c++ 中的 nearbyint()函数

> 原文:[https://www.geeksforgeeks.org/nearbyint-function-in-c/](https://www.geeksforgeeks.org/nearbyint-function-in-c/)

nearbyint()函数在 *cmath* 头文件中定义。该函数使用当前的舍入方法将给定值舍入到一个附近的整数值。当前的舍入方法由 *fegetround* 描述。

**语法:**

```cpp
float nearbyint(float x);

or,
double nearbyint(double x);

or,
long double nearbyint(long double x);

```

**参数:**该函数接受单参数 *x* ，其中包含浮点值。

**返回值:**使用舍入方法将 x 的舍入值返回到附近的整数值。

下面的程序说明了 C++ 中的 nearbyint()函数:

**程序 1:**

```cpp
// C++ program to demonstrate
// example of nearbyint() function.

#include <bits/stdc++.h>
using namespace std;
int main()
{
    float x = 2.7;

    cout << "Value of x = " << x << endl;
    cout << "Round off value of x = " << nearbyint(x);

    return 0;
}
```

**Output:**

```cpp
Value of x = 2.7
Round off value of x = 3

```

**程序 2:**

```cpp
// C++ program to demonstrate
// example of nearbyint() function.

#include <bits/stdc++.h>
using namespace std;
int main()
{
    double x = 3.2;

    cout << "Value of x = " << x << endl;
    cout << "Round off value of x = " << nearbyint(x);

    return 0;
}
```

**Output:**

```cpp
Value of x = 3.2
Round off value of x = 3

```