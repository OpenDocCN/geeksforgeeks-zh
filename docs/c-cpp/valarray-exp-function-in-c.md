# c++ 中的 valarray exp()函数

> 原文:[https://www.geeksforgeeks.org/valarray-exp-function-in-c/](https://www.geeksforgeeks.org/valarray-exp-function-in-c/)

**exp()** 函数在 **valarray** 头文件中定义。这个函数用来计算 e 的幂等于 valarray 中元素的值。

**语法:**

```cpp
exp(varr);
```

**参数:**该函数采用代表 valarray 的强制参数 **varr** 。

**返回:**这个函数返回一个包含所有元素指数值的 valarray。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of exp() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Initializing valarray
    valarray<double>
        varr = { 1, 2, 3, 4, 5 };

    // Declaring new valarray
    valarray<double> varr1;

    // use of exp() function
    varr1 = exp(varr);

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
2.71828 7.38906 20.0855 54.5982 148.413

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of exp() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Initializing valarray
    valarray<double>
        varr = { -1, 0, 3, 0, -5 };

    // Declaring new valarray
    valarray<double> varr1;

    // use of exp() function
    varr1 = exp(varr);

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
0.367879 1 20.0855 1 0.00673795

```