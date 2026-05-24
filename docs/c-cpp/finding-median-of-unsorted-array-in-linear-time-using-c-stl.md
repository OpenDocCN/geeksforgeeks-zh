# 用 C++ STL 求线性时间内未排序数组的中值

> 原文:[https://www . geeksforgeeks . org/find-in-of-unsorted-array-in-time-use-c-STL/](https://www.geeksforgeeks.org/finding-median-of-unsorted-array-in-linear-time-using-c-stl/)

给定一个具有 **N** 元素的未排序的[数组](https://www.geeksforgeeks.org/introduction-to-arrays/) **arr[]** ，任务是找出数组在线性时间复杂度上的[中值。](https://www.geeksforgeeks.org/median/)

**示例:**

> **输入:** N = 5，arr[] = {4，1，2，6，5}
> **输出:** 4
> **解释:**
> 由于 N = 5，这是奇数，因此中位数是排序数组中的第 3 个元素。
> 排序后的 arr[]中的第三个元素是 4。
> 因此中位数为 4。
> 
> **输入:** N = 8，arr[] = {1，3，4，2，6，5，8，7}
> **输出:** 4.5
> **解释:**
> 由于 N = 8，这是偶数，因此中值是排序数组中第 4 个和第 5 个元素的平均值。
> 排序后的数组中第 4 个和第 5 个元素分别为 4 和 5。
> 因此中位数为(4+5)/2 = 4.5。

**方法:**思路是在 [C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 中使用 [nth_element()](https://www.geeksforgeeks.org/stdnth_element-in-cpp/) 函数。

1.  如果数组中的元素数量是奇数，则使用如下所示的**第 N 个元素()**函数找到第**(N/2)**个元素，然后索引 **(N/2)** 处的值是给定数组的中值。

    > 第普通个元素(arr.begin()、arr.begin() + N/2、arr.end())

2.  否则，使用如下所示的**第 N _ element()**函数找到第 **(N/2)个**和**((N–1)/2)个**元素，并找到索引 **(N/2)和((N–1)/2)**处值的平均值，即给定数组的中值。

    > 第普通个元素(arr.begin()、arr.begin() + N/2、arr.end())
    > 第普通个元素(arr.begin()、arr。begin()+(N–1)/2、arr.end())

下面是上述方法的实现:

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function for calculating
// the median
double findMedian(vector<int> a,
                  int n)
{

    // If size of the arr[] is even
    if (n % 2 == 0) {

        // Applying nth_element
        // on n/2th index
        nth_element(a.begin(),
                    a.begin() + n / 2,
                    a.end());

        // Applying nth_element
        // on (n-1)/2 th index
        nth_element(a.begin(),
                    a.begin() + (n - 1) / 2,
                    a.end());

        // Find the average of value at
        // index N/2 and (N-1)/2
        return (double)(a[(n - 1) / 2]
                        + a[n / 2])
               / 2.0;
    }

    // If size of the arr[] is odd
    else {

        // Applying nth_element
        // on n/2
        nth_element(a.begin(),
                    a.begin() + n / 2,
                    a.end());

        // Value at index (N/2)th
        // is the median
        return (double)a[n / 2];
    }
}

// Driver Code
int main()
{
    // Given array arr[]
    vector<int> arr = { 1, 3, 4, 2,
                        7, 5, 8, 6 };

    // Function Call
    cout << "Median = "
         << findMedian(arr, arr.size())
         << endl;
    return 0;
}
```

**Output:**

```cpp
Median = 4.5

```

***时间复杂度:** O(N)
**辅助空间复杂度:** O(1)*