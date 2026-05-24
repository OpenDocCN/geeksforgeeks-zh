# c++ 中 valarray size()函数

> 原文:[https://www.geeksforgeeks.org/valarray-size-function-in-c/](https://www.geeksforgeeks.org/valarray-size-function-in-c/)

**大小()**功能在 **[valarray](https://www.geeksforgeeks.org/std-valarray-class-c/)** 头文件中定义。此函数用于查找 valarray 的大小并返回 valarray 的大小。

**语法:**

```cpp
size_t size() const;
```

**参数:**该函数不取任何参数。

**返回:**该函数返回 valarray 中的元素个数。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of size() function.

#include <bits/stdc++.h>
using namespace std;
int main()
{

    // Initializing  valarray
    valarray<int> varr = { 20, 40, 60, 80 };

    // Displaying size of valarray
    cout << "The size of valarray is: ";
    cout << varr.size();

    cout << endl;

    return 0;
}
```

**Output:**

```cpp
The size of valarray is: 4

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of size() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Initializing  valarray
    valarray<int>
        varr = { -20, 40, -50, 60, 80, 0, 0 };

    // Displaying size of valarray
    cout << "The size of valarray is: ";
    cout << varr.size();

    cout << endl;

    return 0;
}
```

**Output:**

```cpp
The size of valarray is: 7

```