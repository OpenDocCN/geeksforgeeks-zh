# c++ 中的 valarray min()

> 原文:[https://www.geeksforgeeks.org/valarray-min-in-c/](https://www.geeksforgeeks.org/valarray-min-in-c/)

**min()** 功能在 **[valarray 头文件](https://www.geeksforgeeks.org/std-valarray-class-c/)** 中定义。此函数返回 valarray 中包含的最小值。

**语法:**

```cpp
T min() const;
```

**返回:**该函数返回 valarray 中的**最小值**。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of min() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initializing valarray
    valarray<int> varr = { 3, 2, 1, 4, 5 };

    // Displaying minimum element of valarray
    cout << "The smallest element"
         << " of valarray is = "
         << varr.min() << endl;

    return 0;
}
```

**Output:**

```cpp
The smallest element of valarray is = 1

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of min() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initializing valarray
    valarray<int> varr = { 22, 24, 36, 42, 12 };

    // Displaying minimum element of valarray
    cout << "The smallest element "
         << "of valarray is = "
         << varr.min() << endl;

    return 0;
}
```

**Output:**

```cpp
The smallest element of valarray is = 12

```