# valarray asin()函数在 C++ 中

> 原文:[https://www.geeksforgeeks.org/valarray-asin-function-in-c/](https://www.geeksforgeeks.org/valarray-asin-function-in-c/)

**数组**头文件中定义了 **asin()** 函数。此函数用于计算 valarray 中每个元素值的反正弦，并返回一个包含所有元素反正弦的 valarray。

**语法:**

```cpp
asin(varr);

```

**参数:**该函数采用代表 valarray 的强制参数 **varr** 。

**返回:**该函数返回一个包含所有元素反正弦的 valarray。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of asin() function.

#include <bits/stdc++.h>
using namespace std;
int main()
{
    // Initializing valarray
    valarray<double>
        varr = { 0, 0.25, 0.5, 0.75, 1 };

    // Declaring new valarray
    valarray<double> varr1;

    // use of asin() function
    varr1 = asin(varr);

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
0 0.25268 0.523599 0.848062 1.5708

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of asin() function.

#include <bits/stdc++.h>
using namespace std;
int main()
{
    // Initializing valarray
    valarray<double>
        varr = { 0.2, 0.14, 5.0, 0.0 };

    // Declaring new valarray
    valarray<double> varr1;

    // use of asin() function
    varr1 = asin(varr);

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
0.201358 0.140461 nan 0

```