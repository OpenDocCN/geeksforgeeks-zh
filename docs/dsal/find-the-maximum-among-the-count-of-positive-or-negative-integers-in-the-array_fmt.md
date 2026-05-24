# 求数组中正负整数个数的最大值

> 原文: [https://www.geeksforgeeks.org/find-the-maximum-among-the-count-of-positive-or-negative-integers-in-the-array/](https://www.geeksforgeeks.org/find-the-maximum-among-the-count-of-positive-or-negative-integers-in-the-array/)

给定一个由 `N` 个整数组成的[排序数组](https://www.geeksforgeeks.org/program-check-array-sorted-not-iterative-recursive/) `arr[]`，任务是在数组 `arr[]` 的正整数或负整数的计数中找到最大值。

**示例:**

> **输入:** `arr[] = {-9, -7, -4, 1, 5, 8, 9}`
> **输出:** `4`
> **说明:**
> 正数计数为 4，负数计数为 3。所以，4，3 中的最大值是 4。因此，打印 4。
>
> **输入:** `arr[] = {-8, -6, 10, 15}`
> **输出:** `2`

## 逼近

给定的问题可以用[二分搜索法](https://www.geeksforgeeks.org/binary-search/)来解决，思路是先找到数值为正的第一个指标，然后打印 `idx` 和 `(N–idx)` 的最大值作为结果。按照以下步骤解决给定的问题:

*   初始化两个变量，说 `low` 为 `0` 和 `high` 为 `(N–1)`。
*   对给定数组 `arr[]` 执行[二分搜索法](https://www.geeksforgeeks.org/binary-search/)，迭代至 `low <= high` 并遵循以下步骤:
    *   求 `mid` 的值为 `(low + high) / 2`。
    *   如果 `arr[mid]` 的值为正值，则将 `high` 的值更新为 `(mid–1)`，跳过右半部分。否则，通过将 `low` 的值更新为 `(mid + 1)`，跳过左半部分。
*   完成以上步骤后，打印 `low` 和 `(N–low)` 的最大值作为结果。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach

#include "bits/stdc++.h"
using namespace std;

// Function to find the maximum of the
// count of positive or negative elements
int findMaximum(int arr[], int size)
{

    // Initialize the pointers
    int i = 0, j = size - 1, mid;

    while (i <= j) {

        // Find the value of mid
        mid = i + (j - i) / 2;

        // If element is negative then
        // ignore the left half
        if (arr[mid] < 0)
            i = mid + 1;

        // If element is positive then
        // ignore the right half
        else if (arr[mid] > 0)
            j = mid - 1;
    }

    // Return maximum among the count
    // of positive & negative element
    return max(i, size - i);
}

// Driver Code
int main()
{
    int arr[] = { -9, -7, -4, 1, 5, 8, 9 };
    int N = sizeof(arr) / sizeof(arr[0]);

    cout << findMaximum(arr, N);

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.io.*;

public class GFG {

    // Function to find the maximum of the
    // count of positive or negative elements
    static int findMaximum(int arr[], int size)
    {

        // Initialize the pointers
        int i = 0, j = size - 1, mid;

        while (i <= j) {

            // Find the value of mid
            mid = i + (j - i) / 2;

            // If element is negative then
            // ignore the left half
            if (arr[mid] < 0)
                i = mid + 1;

            // If element is positive then
            // ignore the right half
            else if (arr[mid] > 0)
                j = mid - 1;
        }

        // Return maximum among the count
        // of positive & negative element
        return Math.max(i, size - i);
    }

    // Driver Code
    public static void main (String[] args)
    {
        int arr[] = { -9, -7, -4, 1, 5, 8, 9 };
        int N = arr.length;

        System.out.println(findMaximum(arr, N));

    }

}

// This code is contributed by AnkThon
```

## Python 3

```python
# python program for the above approach

# Function to find the maximum of the
# count of positive or negative elements
def findMaximum(arr, size):

    # Initialize the pointers
    i = 0
    j = size - 1

    while (i <= j):

         # Find the value of mid
        mid = i + (j - i) // 2

        # If element is negative then
        # ignore the left half
        if (arr[mid] < 0):
            i = mid + 1

            # If element is positive then
            # ignore the right half
        elif (arr[mid] > 0):
            j = mid - 1

        # Return maximum among the count
        # of positive & negative element
    return max(i, size - i)

# Driver Code
if __name__ == "__main__":

    arr = [-9, -7, -4, 1, 5, 8, 9]
    N = len(arr)

    print(findMaximum(arr, N))

    # This code is contributed by rakeshsahni
```

## C#

```csharp
// C# program for the above approach
using System;

public class GFG
{

    // Function to find the maximum of the
    // count of positive or negative elements
    static int findMaximum(int []arr, int size)
    {

        // Initialize the pointers
        int i = 0, j = size - 1, mid;

        while (i <= j) {

            // Find the value of mid
            mid = i + (j - i) / 2;

            // If element is negative then
            // ignore the left half
            if (arr[mid] < 0)
                i = mid + 1;

            // If element is positive then
            // ignore the right half
            else if (arr[mid] > 0)
                j = mid - 1;
        }

        // Return maximum among the count
        // of positive & negative element
        return Math.Max(i, size - i);
    }

    // Driver Code
    public static void Main (string[] args)
    {
        int []arr = { -9, -7, -4, 1, 5, 8, 9 };
        int N = arr.Length;

        Console.WriteLine(findMaximum(arr, N));
    }
}

// This code is contributed by AnkThon
```

## JavaScript

```javascript
<script>
// Javascript program for the above approach

// Function to find the maximum of the
// count of positive or negative elements
function findMaximum(arr, size)
{

  // Initialize the pointers
  let i = 0,
    j = size - 1,
    mid;

  while (i <= j)
  {

    // Find the value of mid
    mid = i + Math.floor((j - i) / 2);

    // If element is negative then
    // ignore the left half
    if (arr[mid] < 0) i = mid + 1;

    // If element is positive then
    // ignore the right half
    else if (arr[mid] > 0) j = mid - 1;
  }

  // Return maximum among the count
  // of positive & negative element
  return Math.max(i, size - i);
}

// Driver Code
let arr = [-9, -7, -4, 1, 5, 8, 9];
let N = arr.length;

document.write(findMaximum(arr, N));

// This code is contributed by saurabh_jaiswal.
</script>
```

**输出:**

```
4
```

`时间复杂度`: `O(log N)`
`辅助空间`: `O(1)`