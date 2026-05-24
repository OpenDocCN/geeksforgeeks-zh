# valarray tanh()函数在 C++ 中

> 原文:[https://www.geeksforgeeks.org/valarray-tanh-function-in-c/](https://www.geeksforgeeks.org/valarray-tanh-function-in-c/)

**tanh()** 函数在 **valarray** 头文件中定义。此函数用于计算 valarray 中每个元素值的双曲正切值，并返回一个 valarray，其中包含所有元素的双曲正切值。

**语法:**

```cpp
tanh(varr);

```

**参数:**该函数采用代表 valarray 的强制参数 **varr** 。

**返回:**这个函数返回一个包含所有元素双曲正切值的 valarray。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of tanh() function.

#include <bits/stdc++.h>
using namespace std;
int main()
{
    // Initializing valarray
    valarray<double>
        varr = { 0, 0.25, 0.5, 0.75, 1 };

    // Declaring new valarray
    valarray<double> varr1;

    // use of tanh() function
    varr1 = tanh(varr);

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
0 0.244919 0.462117 0.635149 0.761594

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of tanh() function.

#include <bits/stdc++.h>
using namespace std;
int main()
{
    // Initializing valarray
    valarray<double>
        varr = { 0.2, 0.14, 1.0, 0.0 };

    // Declaring new valarray
    valarray<double> varr1;

    // use of tanh() function
    varr1 = tanh(varr);

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
0.197375 0.139092 0.761594 0

```