# c++ 中的 valarray sqrt()函数

> 原文:[https://www.geeksforgeeks.org/valarray-sqrt-function-in-c/](https://www.geeksforgeeks.org/valarray-sqrt-function-in-c/)

**sqrt()** 函数在 **valarray** 头文件中定义。此函数用于计算 valarray 中每个元素的值的平方根。

**语法:**

```cpp
sqrt(varr);

```

**参数:**该函数采用代表 valarray 的强制参数 **varr** 。

**返回:**这个函数返回一个 valarray，包含 valarray 所有元素的平方根。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of sqrt() function.

#include <bits/stdc++.h>
using namespace std;
int main()
{
    // Initializing valarray
    valarray<double>
        varr = { 4, 16, 25, 36, 49 };

    // Declaring new valarray
    valarray<double> varr1;

    // use of sqrt() function
    varr1 = sqrt(varr);

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
2 4 5 6 7

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of sqrt() function.

#include <bits/stdc++.h>
using namespace std;
int main()
{
    // Initializing valarray
    valarray<double>
        varr = { 5, 16, 26, 37, 1 };

    // Declaring new valarray
    valarray<double> varr1;

    // use of sqrt() function
    varr1 = sqrt(varr);

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
2.23607 4 5.09902 6.08276 1

```