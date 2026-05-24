# valarray sin()函数在 C++ 中

> 原文:[https://www.geeksforgeeks.org/valarray-sin-function-in-c/](https://www.geeksforgeeks.org/valarray-sin-function-in-c/)

**sin()** 函数在 **valarray** 头文件中定义。此函数用于计算 valarray 中每个元素的正弦值，并返回包含所有元素正弦值的 valarray。

**语法:**

```cpp
sin(varr);
```

**参数:**该函数采用代表 valarray 的强制参数 **varr** 。

**返回:**这个函数返回一个包含所有元素正弦的 valarray。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of sin() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Initializing valarray
    valarray<double>
        varr = { 0, 0.25, 0.5, 0.75, 1 };

    // Declaring new valarray
    valarray<double> varr1;

    // use of sin() function
    varr1 = sin(varr);

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
0 0.247404 0.479426 0.681639 0.841471

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of sin() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Initializing valarray
    valarray<double>
        varr = { 1.2, 3.14, 5.0, 0.0 };

    // Declaring new valarray
    valarray<double> varr1;

    // use of sin() function
    varr1 = sin(varr);

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
0.932039 0.00159265 -0.958924 0

```