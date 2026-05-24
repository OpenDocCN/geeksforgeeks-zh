# c++ 中 valarray cos()函数

> 原文:[https://www.geeksforgeeks.org/valarray-cos-function-in-c/](https://www.geeksforgeeks.org/valarray-cos-function-in-c/)

**cos()** 函数在 **valarray** 头文件中定义。此函数用于计算 valarray 中每个元素值的余弦值，并返回一个包含所有元素余弦值的 valarray。

**语法:**

```cpp
cos(varr);

```

**参数:**该函数采用代表 valarray 的强制参数 **varr** 。

**返回:**这个函数返回一个包含所有元素余弦的 valarray。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of cos() function.

#include <bits/stdc++.h>
using namespace std;
int main()
{
    // Initializing valarray
    valarray<double>
        varr = { 0, 0.25, 0.5, 0.75, 1 };

    // Declaring new valarray
    valarray<double> varr1;

    // use of cos() function
    varr1 = cos(varr);
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
1 0.968912 0.877583 0.731689 0.540302

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of cos() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initializing valarray
    valarray<double>
        varr = { 1.2, 3.14, 5.0, 0.0 };

    // Declaring new valarray
    valarray<double> varr1;

    // use of cos() function
    varr1 = cos(varr);

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
0.362358 -0.999999 0.283662 1

```