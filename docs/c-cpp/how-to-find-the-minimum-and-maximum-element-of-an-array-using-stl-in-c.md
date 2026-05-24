# 如何用 C++ 中的 STL 求数组的最小和最大元素？

> 原文:[https://www . geesforgeks . org/如何使用 c-in-STL 找到数组的最小和最大元素/](https://www.geeksforgeeks.org/how-to-find-the-minimum-and-maximum-element-of-an-array-using-stl-in-c/)

给定一个数组 arr[]，用 C++ 中的 STL 找到这个数组的最小和最大元素。
**例:**

```cpp
Input: arr[] = {1, 45, 54, 71, 76, 12}
Output: min = 1, max = 76

Input: arr[] = {10, 7, 5, 4, 6, 12}
Output: min = 4, max = 12
```

**进场:**

*   借助于 STL 中提供的 ***Min_element()** 功能，可以找到 min 或最小值元素。
*   借助 STL 中提供的 ***max_element()** 功能，可以找到最大或最大元素。

**语法:**

```cpp
*min_element (first, last);

*max_element (first, last);
```

要使用*min_element()和*max_element()，必须包含“算法”作为头文件。

使用的范围是[第一个，最后一个]，它包含第一个和最后一个之间的所有元素，包括第一个指向的元素，但不包括最后一个指向的元素。

下面是上述方法的实现:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to find the min and max element
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

    // Find the minimum element
    cout << "\nMin Element = "
         << *min_element(arr, arr + n);

    // Find the maximum element
    cout << "\nMax Element = "
         << *max_element(arr, arr + n);
    // Storing the pointer in an address
    int &min = *min_element(arr,arr+n );
    int &max = *max_element(arr,arr+n );
    cout<<"\nFinding the Element using address variable";
    cout<<"\nMin Element = "<<min;
    cout<<"\nMax Element = "<<max;
    return 0;
}
```

**Output**

```cpp
Array: 1 45 54 71 76 12 
Min Element = 1
Max Element = 76
Finding the Element using address variable
Min Element = 1
Max Element = 76
```