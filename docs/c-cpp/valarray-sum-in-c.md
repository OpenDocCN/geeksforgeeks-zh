# c++ 中的 valarray sum()

> 原文:[https://www.geeksforgeeks.org/valarray-sum-in-c/](https://www.geeksforgeeks.org/valarray-sum-in-c/)

**sum()** 函数在 **[valarray 头文件](https://www.geeksforgeeks.org/std-valarray-class-c/)** 中定义。这个函数返回 valarray 中所有元素的总和，就好像是通过以未指定的顺序对一个元素和所有其他元素的副本应用运算符+=来计算的一样。

**语法:**

```cpp
T sum() const;
```

**返回:**该函数返回 valarray 中所有元素的**和。**

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of sum() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Initializing valarray
    valarray<int> varr = { 15, 10, 30, 33, 40 };

    // Displaying sum of valarray
    cout << "The sum of valarray is = "
         << varr.sum() << endl;

    return 0;
}
```

**Output:**

```cpp
The sum of valarray is = 128

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of sum() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Initializing valarray
    valarray<int> varr = { 1, 2, 3, 4, 5 };

    // Displaying sum of valarray
    cout << "The sum of valarray is = "
         << varr.sum() << endl;

    return 0;
}
```

**Output:**

```cpp
The sum of valarray is = 15

```