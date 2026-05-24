# c++ 中复数的 proj()函数

> 原文:[https://www . geesforgeks . org/proj-function-for-complex-numbers-in-c/](https://www.geeksforgeeks.org/proj-function-for-complex-numbers-in-c/)

**proj()** 函数是一个内置函数，在*复杂的*头文件中定义。该函数用于求复数![z  ](img/1859c931c8589697dda65dbf5bf5e51a.png "Rendered by QuickLaTeX.com")在黎曼球面上的投影。
**语法:**

```cpp
template <class T> complex<T> 
            proj (const complex<T>& z);
```

**参数:**

*   **z:** 该方法取一个代表复数的强制参数 **z** 。

**返回值:**该函数返回复数 z 在黎曼球面上的**投影**。
下面的程序说明了 C++ 中的 proj()函数:
**示例 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// example of proj() function

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // defines the complex number: (2 + 2i)
    complex<double> complexnumber(2, 2);

    cout << "proj" << complexnumber << " = "
                   << proj(complexnumber) << endl;

    return 0;
}
```

**Output:** 

```cpp
proj(2,2) = (2,2)
```