# 如何用 C++ 中的 STL 求一个向量的最小和最大元素？

> 原文:[https://www . geesforgeks . org/如何使用 c-in-STL 找到向量的最小和最大元素/](https://www.geeksforgeeks.org/how-to-find-the-minimum-and-maximum-element-of-a-vector-using-stl-in-c/)

给定一个向量，用 C++ 中的 STL 找到这个向量的最小和最大元素。

**例:**

```cpp
Input: {1, 45, 54, 71, 76, 12}
Output: min = 1, max = 76

Input: {10, 7, 5, 4, 6, 12}
Output: min = 1, max = 76

```

**方法:**

*   Or the Min Minimum element can be found by the *** min _ element ()** function provided in STL.
*   Or Max Maximum element can be found with the help of *** max _ element ()** function provided in STL.

**语法:**

```cpp
*min_element (first_index, last_index);

*max_element (first_index, last_index);

```

下面是上述方法的实现:

```cpp
// C++ program to find the min and max element
// of Vector using *min_element() in STL

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

    // Find the min element
    cout << "\nMin Element = "
         << *min_element(a.begin(), a.end());

    // Find the max element
    cout << "\nMax Element = "
         << *max_element(a.begin(), a.end());
    return 0;
}
```

**输出:**

```cpp
Vector: 1 45 54 71 76 12 

Min Element = 1
Max Element = 76

```