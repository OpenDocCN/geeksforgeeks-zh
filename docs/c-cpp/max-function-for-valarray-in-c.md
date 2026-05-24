# c++ 中 valarray 的 max()函数

> 原文:[https://www . geesforgeks . org/max-function-for-valarray-in-c/](https://www.geeksforgeeks.org/max-function-for-valarray-in-c/)

**max()** 函数在 **[valarray](https://www.geeksforgeeks.org/std-valarray-class-c/)** 头文件中定义。此函数返回 valarray 中包含的最大值。

**语法:**

```cpp
T max() const;

```

**参数:**该函数不接受任何参数。

**返回:**该函数返回 valarray 中的最大值。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of max() function.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initializing valarray
    valarray<int> varr = { 3, 2, 1, 4, 5 };

    // Displaying maximum element of valarray
    cout << "The largest element of valarray is = ";
    cout << varr.max() << endl;

    return 0;
}
```

**Output:**

```cpp
The largest element of valarray is = 5

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of max() function.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initializing valarray
    valarray<int> varr = { 22, 24, 36, 42, 12 };

    // Displaying maximum element of valarray
    cout << "The largest element of valarray is = ";
    cout << varr.max() << endl;

    return 0;
}
```

**Output:**

```cpp
The largest element of valarray is = 42

```