# 如何用 C++ 中的 STL 求数组元素的和？

> 原文:[https://www . geeksforgeeks . org/如何使用 c-in-STL 找到数组元素之和/](https://www.geeksforgeeks.org/how-to-find-the-sum-of-elements-of-an-array-using-stl-in-c/)

给定一个数组 arr[]，用 C++ 中的 STL 求出这个数组元素的和。

**例:**

```cpp
Input: arr[] = {1, 45, 54, 71, 76, 12}
Output: 259

Input: arr[] = {1, 7, 5, 4, 6, 12}
Output: 35

```

**逼近:**可以借助 STL 中提供的[累加()](https://www.geeksforgeeks.org/numeric-header-in-c-stl-set-1-accumulate-and-partial_sum/)功能求和。

**语法:**

```cpp
accumulate(first_index, last_index, initial value of sum);

```

下面是上述方法的实现:

```cpp
// C++ program to find the sum
// of Array using accumulate() in STL

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

    // Find the sum
    cout << "\nSum = "
         << accumulate(arr, arr + n, 0);
    return 0;
}
```

**输出:**

```cpp
Array: 1 45 54 71 76 12 
Sum = 259

```