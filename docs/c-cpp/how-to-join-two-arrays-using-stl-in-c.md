# 如何在 C++ 中使用 STL 连接两个数组？

> 原文:[https://www . geeksforgeeks . org/如何使用-stl-in-c/](https://www.geeksforgeeks.org/how-to-join-two-arrays-using-stl-in-c/) 连接两个数组

给定两个数组，在 C++ 中使用 STL 连接这两个数组。

**示例:**

> **输入:**
> arr1[] = {1，45，54，71，76，12}，
> arr2[] = {1，7，5，4，6，12}
> **输出:** {1，4，5，6，7，12，45，54，71，76}
> 
> **输入:**
> arr1[] = {1，7，5，4，6，12}，
> arr2[] = {10，12，11 }
> T5】输出: {1，4，5，6，7，10，11，12}

**方式:**连接可以借助 STL 中提供的 [set_union()](https://www.geeksforgeeks.org/std-set_union-in-cpp/) 功能完成。

**语法:**

```cpp
set_union (InputIterator1 first1, InputIterator1 last1,
           InputIterator2 first2, InputIterator2 last2,
           OutputIterator result);

```

下面是上述方法的实现:

```cpp
// C++ program to join two Arrays
// using set_union() in STL

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
    // to store the merged values
    // and an iterator
    // to traverse this vector
    vector<int> v(n1 + n2);
    vector<int>::iterator it, st;

    it = set_union(arr1, arr1 + n1,
                   arr2, arr2 + n2,
                   v.begin());

    // Print the merged array
    cout << "\nAfter joining:\n";
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

After joining:
1, 4, 5, 6, 7, 12, 45, 54, 71, 76,

```