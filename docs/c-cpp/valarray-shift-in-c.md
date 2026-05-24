# c++ 中的 valarray shift()

> 原文:[https://www.geeksforgeeks.org/valarray-shift-in-c/](https://www.geeksforgeeks.org/valarray-shift-in-c/)

**shift()** 功能在 **[valarray 头文件](https://www.geeksforgeeks.org/std-valarray-class-c/)** 中定义。该函数返回一个相同大小的新 valarray，其元素位置被 **n** 个元素移动。如果 n 为负，则应用右移，如果 n 为正，则应用左移。

**语法:**

```cpp
valarray shift (int n) const;
```

**参数:**该方法接受一个强制参数 **n** ，代表要移位的元素数量。

**返回:**该函数在元素移动后返回**新的 valarray** 。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of shift() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initializing valarray
    valarray<int> varr = { 3, 2, 5, 4, 1 };

    // Declaring new valarray
    valarray<int> varr1;

    // using shift() to shift elements to left
    // shifts valarray by 3 position
    varr1 = varr.shift(3);

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
The new valarray after shifting is = 4 1 0 0 0

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of shift() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initializing valarray
    valarray<int> varr = { 3, 2, 5, 4, 1 };

    // Declaring new valarray
    valarray<int> varr1;

    // using shift() to shift elements to right
    // shifts valarray by 2 position
    varr1 = varr.shift(-2);

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
The new valarray after shifting is = 0 0 3 2 5

```