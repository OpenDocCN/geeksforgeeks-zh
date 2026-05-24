# 如何用 C++ 中的 STL 找到两个数组之间的公共元素？

> 原文:[https://www . geesforgeks . org/如何使用-stl-in-c/](https://www.geeksforgeeks.org/how-to-find-common-elements-between-two-arrays-using-stl-in-c/) 在两个数组之间查找公共元素

给定两个数组，在 C++ 中使用 STL 找到这两个数组之间的公共元素。

**示例:**

```cpp
Input: 
arr1[] = {1, 45, 54, 71, 76, 12}, 
arr2[] = {1, 7, 5, 4, 6, 12}
Output: {1, 12}

Input: 
arr1[] = {1, 7, 5, 4, 6, 12}, 
arr2[] = {10, 12, 11}
Output: {1, 4, 12}

```

**方法:**常用元素可以借助 STL 中提供的**set _ 交集()**功能找到。

**语法:**

```cpp
set_intersection (InputIterator1 first1, InputIterator1 last1,
           InputIterator2 first2, InputIterator2 last2,
           OutputIterator result);

```

```cpp
// C++ program to find common elements
// between two Arrays using STL

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Get the array
    int arr1[] = { 1, 45, 54, 71, 76, 12 };
    int arr2[] = { 1, 7, 5, 4, 6, 12 };

    // Compute the sizes
    int n1 = sizeof(arr1) / sizeof(arr1[0]);
    int n2 = sizeof(arr2) / sizeof(arr2[0]);

    // Sort the arrays
    sort(arr1, arr1 + n1);
    sort(arr2, arr2 + n2);

    // Print the array
    cout << "First Array: ";
    for (int i = 0; i < n1; i++)
        cout << arr1[i] << " ";
    cout << endl;

    cout << "Second Array: ";
    for (int i = 0; i < n2; i++)
        cout << arr2[i] << " ";
    cout << endl;

    // Initialise a vector
    // to store the common values
    // and an iterator
    // to traverse this vector
    vector<int> v(n1 + n2);
    vector<int>::iterator it, st;

    it = set_intersection(arr1, arr1 + n1,
                          arr2, arr2 + n2,
                          v.begin());

    cout << "\nCommon elements:\n";
    for (st = v.begin(); st != it; ++ st)
        cout << *st << ", ";
    cout << '\n';

    return 0;
}
```

**Output:**

```cpp
First Array: 1 12 45 54 71 76 
Second Array: 1 4 5 6 7 12 

Common elements:
1, 12,

```