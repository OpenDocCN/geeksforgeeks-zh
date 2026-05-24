# c++ 中 valarray pow()函数

> 原文:[https://www.geeksforgeeks.org/valarray-pow-function-in-c/](https://www.geeksforgeeks.org/valarray-pow-function-in-c/)

**pow()** 函数在 **valarray** 头文件中定义。该函数返回一个 valarray，其中包含所有元素的幂运算结果，顺序相同。
**语法:**

```cpp
pow(varr, n);

```

**参数:**

*   **varr:** 这代表 valarray 对象。
*   **n:** 表示指数值。

**返回:**该函数返回一个 valarray，其中包含所有元素的幂运算结果。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of pow() function.

#include <bits/stdc++.h>
using namespace std;
int main()
{
    // Initializing valarray
    valarray<int> varr = { -1, 2, 3, 4, -5 };

    // Declaring new valarray
    valarray<int> varr1;

    // use of pow() function
    varr1 = pow(varr, 3);

    // Displaying new elements value
    cout << "The new valarray with"
         << " manipulated values is : "
         << endl;

    for (int& x : varr1) {
        cout << x << " ";
    }

    cout << endl;

    return 0;
}
```

**Output:**

```cpp
The new valarray with manipulated values is : 
-1 8 27 64 -125

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of pow() function.

#include <bits/stdc++.h>
using namespace std;
int main()
{
    // Initializing valarray
    valarray<int> varr = { -1, 6, 3, 4, 5 };

    // Declaring new valarray
    valarray<int> varr1;

    // use of pow() function
    varr1 = pow(varr, 2);

    // Displaying new elements value
    cout << "The new valarray with"
         << " manipulated values is : "
         << endl;

    for (int& x : varr1) {
        cout << x << " ";
    }

    cout << endl;

    return 0;
}
```

**Output:**

```cpp
The new valarray with manipulated values is : 
1 36 9 16 25

```