# valarray tan()函数在 C++ 中

> 原文:[https://www.geeksforgeeks.org/valarray-tan-function-in-c/](https://www.geeksforgeeks.org/valarray-tan-function-in-c/)

**tan()** 函数在 **valarray** 头文件中定义。此函数用于计算 valarray 中每个元素值的正切值，并返回一个包含所有元素正切值的 valarray。

**语法:**

```cpp
tan(varr);

```

**参数:**该函数采用代表 valarray 的强制参数 **varr** 。

**返回:**这个函数返回一个包含所有元素切线的 valarray。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of tan() function.

#include <bits/stdc++.h>
using namespace std;
int main()
{
    // Initializing valarray
    valarray<double>
        varr = { 0, 0.25, 0.5, 0.75, 1 };

    // Declaring new valarray
    valarray<double> varr1;

    // use of tan() function
    varr1 = tan(varr);

    // Displaying new elements value
    cout << "The new valarray with"
         << " manipulated values is : "
         << endl;

    for (double& x : varr1) {
        cout << x << " ";
    }

    cout << endl;

    return 0;
}
```

**Output:**

```cpp
The new valarray with manipulated values is : 
0 0.255342 0.546302 0.931596 1.55741

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of tan() function.

#include <bits/stdc++.h>
using namespace std;
int main()
{
    // Initializing valarray
    valarray<double> varr = { 1.2, 3.14, 5.0, 0.0 };

    // Declaring new valarray
    valarray<double> varr1;

    // use of tan() function
    varr1 = tan(varr);

    // Displaying new elements value
    cout << "The new valarray with"
         << " manipulated values is : "
         << endl;

    for (double& x : varr1) {
        cout << x << " ";
    }

    cout << endl;

    return 0;
}
```

**Output:**

```cpp
The new valarray with manipulated values is : 
2.57215 -0.00159265 -3.38052 0

```