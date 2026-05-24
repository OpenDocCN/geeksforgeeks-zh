# c++ 中的 scalbn()函数

> 原文:[https://www.geeksforgeeks.org/scalbn-function-in-c/](https://www.geeksforgeeks.org/scalbn-function-in-c/)

**scalbn()** 函数在 **cmath** 头文件中定义。这个函数用来计算给定的数 x 和 FLT 基数的乘积。

**语法:-**

```cpp
float scalbn(float x, int n); 
```

**或**

```cpp
double scalbn(double x, int n); 
```

**或**

```cpp
long double scalbn(long double x, int n); 
```

**或**

```cpp
double scalbn(integral x, int n);  
```

**参数:-** 该方法取两个参数:

*   **x:** 这表示有效数的值。
*   **n:** 这代表指数的值。

**返回值:**该函数借助公式返回**给定数 x 与 FLT_RADIX 的乘积，该乘积的幂为 n。**:

```cpp
scalbn(x, n) = x * FLT_RADIXn
```

以下程序说明了上述功能

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of scalbn() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
    int n = 7;
    int x = 5;
    int ans;

    ans = scalbn(x, n);
    cout << x << " * "
         << FLT_RADIX << "^"
         << n << " = "
         << ans << endl;

    return 0;
}
```

**Output:**

```cpp
5 * 2^7 = 640

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of scalbn() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
    int n = 7;
    double x = 3.9;
    int ans;

    ans = scalbn(x, n);
    cout << x << " * "
         << FLT_RADIX << "^"
         << n << " = "
         << ans << endl;

    return 0;
}
```

**Output:**

```cpp
3.9 * 2^7 = 499

```