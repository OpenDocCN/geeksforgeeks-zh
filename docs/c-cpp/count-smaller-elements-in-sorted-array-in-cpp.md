# 计算 C++ 中排序数组中较小的元素

> 原文:[https://www . geeksforgeeks . org/count-较小元素在排序数组中-in-cpp/](https://www.geeksforgeeks.org/count-smaller-elements-in-sorted-array-in-cpp/)

给定一个排序的数组和一个数字 x，计算给定数组中小于 x 的元素。

示例:

```cpp
Input : arr[] = {10, 20, 30, 40, 50}
            x = 45
Output : 4
There are 4 elements smaller than 45.

Input : arr[] = {10, 20, 30, 40, 50}
            x = 40
Output : 3
There are 3 elements smaller than 40.

```

我们可以用 C++ 中的 upper_bound()来快速找到结果。它返回迭代器(或指针)到大于给定数字的第一个元素。如果所有元素都变小，则返回数组的大小。如果所有元素都大于，则返回 0。

```cpp
// CPP program to count smaller elements
// in an array.
#include <bits/stdc++.h>
using namespace std;

int countSmaller(int arr[], int n, int x)
{
   return upper_bound(arr, arr+n, x) - arr;
}

// Driver code
int main()
{
    int arr[] = { 10, 20, 30, 40, 50 };
    int n = sizeof(arr)/sizeof(arr[0]);
    cout << countSmaller(arr, n, 45) << endl; 
    cout << countSmaller(arr, n, 55) << endl;
    cout << countSmaller(arr, n, 4) << endl;
    return 0;
}
```

**输出:**

```cpp
4
5
0

```

时间复杂度:0(对数 n)