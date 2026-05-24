# 如何在 C++ 中使用 STL 反转数组？

> 原文:[https://www . geesforgeks . org/如何使用 c-in-STL 反转数组/](https://www.geeksforgeeks.org/how-to-reverse-an-array-using-stl-in-c/)

给定一个数组 arr[]，在 C++ 中使用 STL 反转这个数组。

**例:**

```cpp
Input: arr[] = {1, 45, 54, 71, 76, 12}
Output: {12, 76, 71, 54, 45, 1}

Input: arr[] = {1, 7, 5, 4, 6, 12}
Output: {12, 6, 4, 5, 7, 1}

```

**进场:**可以借助 STL 提供的 reverse()功能进行倒车。

**语法:**

```cpp
reverse(start_index, last_index);

```

```cpp
// C++ program to reverse Array
// using reverse() in STL

#include <algorithm>
#include <iostream>
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

    // Reverse the array
    reverse(arr, arr + n);

    // Print the reversed array
    cout << "\nReversed Array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    return 0;
}
```

**输出:**

```cpp
Array: 1 45 54 71 76 12 
Reversed Array: 12 76 71 54 45 1

```