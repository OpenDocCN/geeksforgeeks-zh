# c++ 中 valarray 的 cshift()函数

> 原文:[https://www . geesforgeks . org/cs shift-function-for-valarray-in-c/](https://www.geeksforgeeks.org/cshift-function-for-valarray-in-c/)

**csshift()**函数在 **[valarray](https://www.geeksforgeeks.org/std-valarray-class-c/)** 头文件中定义。该函数返回一个相同大小的新 valarray，其元素的位置被 **n** 个元素循环移位。如果 n 为负，则应用右移，如果 n 为正，则应用左移。

**语法:**

```cpp
valarray cshift (int n) const;

```

**参数:**

*   **n:** 表示要移位的元素个数。

**返回:**该函数循环移位元素后返回新的 valarray。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of cshift() function.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initializing valarray
    valarray<int> varr = { 3, 2, 5, 4, 1 };

    // Declaring new valarray
    valarray<int> varr1;

    // using cshift() to shift elements to left
    // shifts valarray by 3 position
    varr1 = varr.cshift(3);

    // Displaying elements of valarray after shifting
    cout << "The new valarray after shifting is = ";
    for (int& x : varr1)
        cout << x << " ";
    cout << endl;

    return 0;
}
```

**Output:**

```cpp
The new valarray after shifting is = 4 1 3 2 5

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of cshift() function.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initializing valarray
    valarray<int> varr = { 3, 2, 5, 4, 1 };

    // Declaring new valarray
    valarray<int> varr1;

    // using cshift() to shift elements to right
    // shifts valarray by 3 position
    varr1 = varr.cshift(-3);

    // Displaying elements of valarray after shifting
    cout << "The new valarray after shifting is = ";
    for (int& x : varr1)
        cout << x << " ";
    cout << endl;

    return 0;
}
```

**Output:**

```cpp
The new valarray after shifting is = 5 4 1 3 2

```