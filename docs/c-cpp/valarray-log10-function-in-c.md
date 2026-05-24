# valarray log10()函数在 C++ 中

> 原文:[https://www.geeksforgeeks.org/valarray-log10-function-in-c/](https://www.geeksforgeeks.org/valarray-log10-function-in-c/)

**log10()** 函数在 **valarray** 头文件中定义。此函数用于计算 valarray 中元素值的普通对数。

**语法:**

```cpp
log10(varr);
```

**参数:**该函数采用代表 valarray 的强制参数 **varr** 。

**返回:**这个函数返回一个 valarray，包含所有元素的公共对数。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of log10() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Initializing valarray
    valarray<double> varr = { 1, 2, 3, 4, 5 };

    // Declaring new valarray
    valarray<double> varr1;

    // use of log10() function
    varr1 = log10(varr);

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
0 0.30103 0.477121 0.60206 0.69897

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of log10() function.

#include <bits/stdc++.h>
using namespace std;
int main()
{

    // Initializing valarray
    valarray<double>
        varr = { -1, 6, 3, 45, 5 };

    // Declaring new valarray
    valarray<double> varr1;

    // use of log10() function
    varr1 = log10(varr);

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
nan 0.778151 0.477121 1.65321 0.69897

```