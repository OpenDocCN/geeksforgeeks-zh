# 如何用 C++ 中的 STL 求一个向量的最大元素？

> 原文:[https://www . geesforgeks . org/如何使用 c-in-STL 找到向量的最大元素/](https://www.geeksforgeeks.org/how-to-find-the-maximum-element-of-a-vector-using-stl-in-c/)

给定一个向量，用 C++ 中的 STL 找到这个向量的最大元素。

**例:**

```cpp
Input: {1, 45, 54, 71, 76, 12}
Output: 76

Input: {1, 7, 5, 4, 6, 12}
Output: 12

```

**逼近:**借助 STL 中提供的*max_element()函数可以找到 Max 或 Maximum 元素。

**语法:**

```cpp
*max_element (first_index, last_index);

```

```cpp
// C++ program to find the max
// of Array using *max_element() in STL

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Get the vector
    vector<int> a = { 1, 45, 54, 71, 76, 12 };

    // Print the vector
    cout << "Vector: ";
    for (int i = 0; i < a.size(); i++)
        cout << a[i] << " ";
    cout << endl;

    // Find the max element
    cout << "\nMax Element = "
         << *max_element(a.begin(), a.end());
    return 0;
}
```

**输出:**

```cpp
Vector: 1 45 54 71 76 12 

Max Element = 76

```