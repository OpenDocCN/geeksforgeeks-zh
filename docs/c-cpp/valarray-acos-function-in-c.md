# valarray acos()函数在 C++ 中

> 原文:[https://www.geeksforgeeks.org/valarray-acos-function-in-c/](https://www.geeksforgeeks.org/valarray-acos-function-in-c/)

**acos()** 函数在 **valarray** 头文件中定义。此函数用于计算 valarray 中每个元素的值的弧余弦，并返回一个包含所有元素的弧余弦的 valarray。

**语法:**

```cpp
acos(varr);
```

**参数:**该函数采用代表 valarray 的强制参数 **varr** 。

**返回:**这个函数返回一个包含所有元素的弧余弦的 valarray。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of acos() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Initializing valarray
    valarray<double>
        varr = { 0, 0.25, 0.5, 0.75, 1 };

    // Declaring new valarray
    valarray<double> varr1;

    // use of acos() function
    varr1 = acos(varr);

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
1.5708 1.31812 1.0472 0.722734 0

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of acos() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initializing valarray
    valarray<double>
        varr = { 0.2, 0.14, 5.0, 0.0 };

    // Declaring new valarray
    valarray<double> varr1;

    // use of acos() function
    varr1 = acos(varr);

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
1.36944 1.43033 nan 1.5708

```