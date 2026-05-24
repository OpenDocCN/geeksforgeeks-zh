# 如何在 C++ 中使用 STL 对数组进行排序？

> 原文:[https://www . geesforgeks . org/如何使用 c-in-STL 对数组进行排序/](https://www.geeksforgeeks.org/how-to-sort-an-array-using-stl-in-c/)

给定一个数组 arr[]，用 C++ 中的 STL 对这个数组进行排序。

**例:**

```cpp
Input: arr[] = {1, 45, 54, 71, 76, 12}
Output: {1, 12, 45, 54, 71, 76}

Input: arr[] = {1, 7, 5, 4, 6, 12}
Output: {1, 4, 5, 6, 7, 12}

```

**方式:**排序可以借助 STL 中提供的 [sort()](https://www.geeksforgeeks.org/sort-c-stl/) 功能完成。

**语法:**

```cpp
sort(arr, arr + n);

```

```cpp
// C++ program to sort Array
// using sort() in STL

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Get the array
    int arr[] = { 1, 45, 54, 71, 76, 12 };

    // Find the size of the array
    int n = sizeof(arr) / sizeof(arr[0]);

    // Print the array
    cout << "Array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    cout << endl;

    // Sort the array
    sort(arr, arr + n);

    // Print the sorted array
    cout << "Sorted Array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    cout << endl;

    return 0;
}
```

**输出:**

```cpp
Array: 1 45 54 71 76 12 
Sorted Array: 1 12 45 54 71 76

```