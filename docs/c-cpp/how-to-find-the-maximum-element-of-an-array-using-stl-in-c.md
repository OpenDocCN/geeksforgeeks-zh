# 如何用 C++ 中的 STL 求数组的最大元素？

> 原文:[https://www . geesforgeks . org/如何使用 c 语言中的 stl 找到数组的最大元素/](https://www.geeksforgeeks.org/how-to-find-the-maximum-element-of-an-array-using-stl-in-c/)

给定一个数组 arr[]，用 C++ 中的 STL 找到这个数组的最大元素。

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
// of Array using sort() in STL

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Get the array
    int arr[] = { 1, 45, 54, 71, 76, 12 };

    // Compute the sizes
    int n = sizeof(arr) / sizeof(arr[0]);

    // Print the array
    cout << "Array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";

    // Find the maximum element
    cout << "\nMax Element = "
         << *max_element(arr, arr + n);
    return 0;
}
```

**输出:**

```cpp
Array: 1 45 54 71 76 12 
Max Element = 76

```