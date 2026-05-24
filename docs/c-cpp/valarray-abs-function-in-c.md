# valarray abs()函数在 C++ 中

> 原文:[https://www.geeksforgeeks.org/valarray-abs-function-in-c/](https://www.geeksforgeeks.org/valarray-abs-function-in-c/)

**abs()** 功能在 **valarray** 头文件中定义。此函数用于计算 valarray 中每个元素的绝对值，并返回包含所有元素绝对值的 valarray。

**语法:**

```cpp
abs(varr);
```

**参数:**该函数采用代表 valarray 的强制参数 **varr** 。

**返回:**这个函数返回一个包含所有元素绝对值的 valarray。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of abs() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initializing valarray
    valarray<int>
        varr = { 20, 12, -20, 0, -30 };

    // Declaring new valarray
    valarray<int> varr1;

    // use of abs() function
    // for finding abs value
    varr1 = abs(varr);

    // Displaying new elements value
    cout << "The new valarray with"
         << " manipulated values is : ";

    for (int& x : varr1) {
        cout << x << " ";
    }

    cout << endl;

    return 0;
}
```

**Output:**

```cpp
The new valarray with manipulated values is : 20 12 20 0 30

```

**实施例 2:-**

```cpp
// c++ program to demonstrate
// example of abs() function.

#include <bits/stdc++.h>
using namespace std;
int main()
{
    // Initializing valarray
    valarray<int>
        varr = { -36, -369, -20, 0, -30 };

    // Declaring new valarray
    valarray<int> varr1;

    // use of abs() function
    // for finding abs value
    varr1 = abs(varr);

    // Displaying new elements value
    cout << "The new valarray"
         << " with manipulated values is : ";

    for (int& x : varr1) {
        cout << x << " ";
    }

    cout << endl;

    return 0;
}
```

**Output:**

```cpp
The new valarray with manipulated values is : 36 369 20 0 30

```