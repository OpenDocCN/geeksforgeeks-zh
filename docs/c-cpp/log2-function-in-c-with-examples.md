# log2()函数在 C++ 中的应用举例

> 原文:[https://www . geeksforgeeks . org/log 2-c 中的函数-示例/](https://www.geeksforgeeks.org/log2-function-in-c-with-examples/)

[C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中 [cmath 头文件](https://www.geeksforgeeks.org/c-mathematical-functions/)的函数 **log2()** 用于查找传递参数的以**为基 2** 的对数值。

**语法:**

```cpp
log2(x)
```

**参数:**该函数取一个值 **x** ，在**【0，∩】**的范围内，要找到其对数值。

**返回类型:**根据以下条件，以双精度、浮点或长双精度类型返回对数值:

*   **如果 x > 1:** 则返回 x 的正对数值
*   **如果 x 等于 1:** 则返回 0。
*   **如果 0 < x < 1:** 则返回 x 的负对数值
*   **如果 x 等于 0:** 则返回负无穷大(**-∩**)。
*   **如果 x < 0:** 则返回 NaN(不是数字)。

以下示例演示了 log2()方法的使用:

**例 1:**

```cpp
// C++ program to illustrate log2() function

#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    long b = 16;
    float c = 2.5;
    double d = 10.35;
    long double e = 25.5;

    // Logarithmic value of long datatype
    cout << log2(b) << "\n";

    // Logarithmic value of float datatype
    cout << log2(c) << "\n";

    // Logarithmic value of double datatype
    cout << log2(d) << "\n";

    // Logarithmic value of long double datatype
    cout << log2(e) << "\n";

    return 0;
}
```

**输出:**

```cpp
4
1.32193
3.37156
4.67243

```

**例 2:**

```cpp
// C++ program to illustrate log2() function

#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    // To show extreme cases
    int a = 0;
    int b = -16;

    // Logarithmic value of 0
    cout << log2(a) << "\n";

    // Logarithmic value of negative value
    cout << log2(b) << "\n";

    return 0;
}
```

**输出:**

```cpp
-inf
nan

```

**参考:**T2】http://www.cplusplus.com/reference/cmath/log2/