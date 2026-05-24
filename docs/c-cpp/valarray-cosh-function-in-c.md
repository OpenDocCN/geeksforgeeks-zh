# c++ 中 valarray cosh()函数

> 原文:[https://www.geeksforgeeks.org/valarray-cosh-function-in-c/](https://www.geeksforgeeks.org/valarray-cosh-function-in-c/)

**cosh()** 函数在 **valarray** 头文件中定义。此函数用于计算 valarray 中每个元素值的双曲余弦值，并返回一个包含所有元素的双曲余弦值的 valarray。

**语法:**

```cpp
cosh(varr);

```

**参数:**该函数采用代表 valarray 的强制参数 **varr** 。

**返回:**这个函数返回一个包含所有元素的双曲余弦值的 valarray。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of cosh() function.

#include <bits/stdc++.h>
using namespace std;
int main()
{
    // Initializing valarray
    valarray<double>
        varr = { 0, 0.25, 0.5, 0.75, 1 };

    // Declaring new valarray
    valarray<double> varr1;

    // use of cosh() function
    varr1 = cosh(varr);
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
1 1.03141 1.12763 1.29468 1.54308

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of cosh() function.

#include <bits/stdc++.h>
using namespace std;
int main()
{
    // Initializing valarray
    valarray<double>
        varr = { 0.2, 0.14, 1.0, 0.0 };

    // Declaring new valarray
    valarray<double> varr1;

    // use of cosh() function
    varr1 = cosh(varr);
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
1.02007 1.00982 1.54308 1

```