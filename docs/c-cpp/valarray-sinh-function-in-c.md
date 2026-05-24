# c++ 中 valarray sinh()函数

> 原文:[https://www.geeksforgeeks.org/valarray-sinh-function-in-c/](https://www.geeksforgeeks.org/valarray-sinh-function-in-c/)

**sinh()** 函数在 **valarray** 头文件中定义。此函数用于计算 valarray 中每个元素值的双曲正弦值，并返回一个包含所有元素的双曲正弦值的 valarray。

**语法:**

```cpp
sinh(varr);
```

**参数:**该函数采用代表 valarray 的强制参数 **varr** 。

**返回:**这个函数返回一个包含所有元素双曲正弦值的 valarray。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of sinh() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Initializing valarray
    valarray<double>
        varr = { 0, 0.25, 0.5, 0.75, 1 };

    // Declaring new valarray
    valarray<double> varr1;

    // use of sinh() function
    varr1 = sinh(varr);

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
0 0.252612 0.521095 0.822317 1.1752

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of sinh() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Initializing valarray
    valarray<double>
        varr = { 0.2, 0.14, 1.0, 0.0 };

    // Declaring new valarray
    valarray<double> varr1;

    // use of sinh() function
    varr1 = sinh(varr);

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
0.201336 0.140458 1.1752 0

```