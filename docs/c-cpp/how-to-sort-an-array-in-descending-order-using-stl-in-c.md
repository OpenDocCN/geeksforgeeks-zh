# 如何在 C++ 中使用 STL 对数组进行降序排序？

> 原文:[https://www . geesforgeks . org/如何使用-stl-in-c 对数组进行降序排序/](https://www.geeksforgeeks.org/how-to-sort-an-array-in-descending-order-using-stl-in-c/)

给定一个数组 arr[]，用 C++ 中的 STL 对这个数组进行降序排序。

**例:**

```cpp
Input: arr[] = {1, 45, 54, 71, 76, 12}
Output: {76, 71, 54, 45, 12, 1}

Input: arr[] = {1, 7, 5, 4, 6, 12}
Output: {12, 7, 6, 5, 4, 1}

```

**方式:**排序可以借助 STL 中提供的 [sort()](https://www.geeksforgeeks.org/sort-c-stl/) 功能完成。

**语法:**

```cpp
sort(arr, arr + n, greater<T>());

```

```cpp
// C++ program to sort Array
// in descending order
// using sort() in STL

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

    // Sort the array in descending order
    sort(arr, arr + n, greater<int>());

    // Print the sorted array
    cout << "\nDescending Sorted Array:\n";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    return 0;
}
```

**输出:**

```cpp
Array: 1 45 54 71 76 12 
Descending Sorted Array:
76 71 54 45 12 1

```