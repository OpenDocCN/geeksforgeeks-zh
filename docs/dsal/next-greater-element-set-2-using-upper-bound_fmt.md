# 下一个更大的元素|集合 2(使用上限)

> 原文: [https://www.geeksforgeeks.org/next-greater-element-set-2-using-upper-bound/](https://www.geeksforgeeks.org/next-greater-element-set-2-using-upper-bound/)

## 问题描述

给定一个由 `n` 个整数组成的数组 `arr[]`。任务是使用 `upper_bound()` 函数为数组中的每个数组元素找到第一个较大的元素。如果任何数组元素都没有更大的元素，返回 `-1`。

## 示例

**输入:** `n = 7`，`arr[] = {4, 7, 3, 1, 3, 2, 5}`
**输出:** `7 -1 4 4 4 4 7`
**解释:** 第一、第三、第四、第五、第六和最后一个元素的第一个较大元素是 7、4、4、4 和 7。`arr[]` 的第二个元素本身没有第一个更大的元素。

**输入:** `n = 4`，`arr[] = {2, 8, 8, 1}`
**输出:** `8 -1 -1 2`
**说明:** 第一个和最后一个元素的第一个较大元素是 8 和 2。`arr[]` 的第二个和第三个元素本身没有第一个更大的元素。

## 方法

天真方法和堆栈方法在本文的第 1 集中讨论。这里，我们讨论了使用 `upper_bound()` 来求解它的方法。

因为 `upper_bound()` 不能应用于未排序的数组。这个想法是试图修改数组，使它变得有序。因此，创建一个数组让我们把它命名为 `copy[]`，它将有它的元素在一个排序的方式。首先用 `0` 初始化 `copy[]`，并将 `copy[]` 的每个元素更新为: `copy[i] = max(copy[i-1], arr[i])`。现在，`upper_bound()` 可以应用在 `copy[]` 中，并为每个 `arr[i]` 找到第一个更大的元素。按照以下步骤解决问题:

*   初始化一个数组 `copy[n]`，用值 `0` 初始化。
*   使用变量 `i` 迭代范围 `[1, n)`，并执行以下步骤:
    *   将 `copy[i]` 的值设置为 `copy[i-1]` 或 `arr[i]` 的最大值。
*   使用变量 `i` 迭代范围 `[0, n)`，并执行以下步骤:
    *   将变量 `high` 初始化为 `copy[]` 数组中 `arr[i]` 的上限。
    *   如果 `high` 等于 `n`，则打印 `-1`，否则打印 `arr[high]`。

下面是上述方法的实现:

### C++

```cpp
// c++ implementation of  the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find first greater
// element for every element of array
void FirstGreater(int arr[], int n)
{

    // Creating copy array
    int copy[n];

    // Initializing all element of it with zero
    memset(copy, 0, sizeof(copy));

    copy[0] = arr[0];

    for (int i = 1; i < n; i++) {

        // Updating element of copy[]
        copy[i] = max(copy[i - 1], arr[i]);
    }

    for (int i = 0; i < n; i++) {

        // High stores the index of first greater
        // for every element of arr[]
        int high
            = upper_bound(copy,
                          copy + n, arr[i])
              - copy;

        // If there no element
        // is greater than arr[i]
        // print -1
        if (high == n) {
            cout << "-1"
                 << " ";
        }

        // Otherwisw print the first element
        // which is greater than arr[i]
        else {
            cout << arr[high] << " ";
        }
    }
}

// Driver Code
int main()
{

    int arr[] = { 4, 7, 3, 1, 3, 2, 5 };
    int n = sizeof(arr) / sizeof(arr[0]);
    FirstGreater(arr, n);
    return 0;
}
```

### Java

```java
// Java code for the above approach
import java.io.*;
class GFG {
    static int upper_bound(int arr[], int N, int X)
    {
        int mid;

        // Initialise starting index and
        // ending index
        int low = 0;
        int high = N;

        // Till low is less than high
        while (low < high)
        {

            // Find the middle index
            mid = low + (high - low) / 2;

            // If X is greater than or equal
            // to arr[mid] then find
            // in right subarray
            if (X >= arr[mid]) {
                low = mid + 1;
            }

            // If X is less than arr[mid]
            // then find in left subarray
            else {
                high = mid;
            }
        }

        // if X is greater than arr[n-1]
        if (low < N && arr[low] <= X) {
            low++;
        }

        // Return the upper_bound index
        return low;
    }

    // Function to find first greater
    // element for every element of array
    static void FirstGreater(int arr[], int n)
    {

        // Creating copy array
        int copy[] = new int[n];

        copy[0] = arr[0];
        for (int i = 1; i < n; i++)
        {

            // Updating element of copy[]
            copy[i] = Math.max(copy[i - 1], arr[i]);
        }
        for (int i = 0; i < n; i++)
        {

            // High stores the index of first greater
            // for every element of arr[]
            int high
                = upper_bound(copy, copy.length, arr[i]);

            // If there no element
            // is greater than arr[i]
            // print -1
            if (high == n) {
                System.out.print("-1"
                                 + " ");
            }

            // Otherwisw print the first element
            // which is greater than arr[i]
            else {
                System.out.print(arr[high] + " ");
            }
        }
    }

    // Driver Code
    public static void main(String[] args)
    {
        int arr[] = { 4, 7, 3, 1, 3, 2, 5 };
        int n = arr.length;
        FirstGreater(arr, n);
    }
}

// This code is contributed by Potta Lokesh
```

### Python 3

```python
# Python 3 implementation of  the above approach
import bisect

# Function to find first greater
# element for every element of array
def FirstGreater(arr, n):

    # Creating copy array
    copy = [0]*n

    copy[0] = arr[0]

    for i in range(1, n):

        # Updating element of copy[]
        copy[i] = max(copy[i - 1], arr[i])

    for i in range(n):

        # High stores the index of first greater
        # for every element of arr[]
        high = bisect.bisect_right(copy, arr[i], 0, n)

        # If there no element
        # is greater than arr[i]
        # print -1
        if (high == n):
            print("-1", end=" ")

        # Otherwisw print the first element
        # which is greater than arr[i]
        else:
            print(arr[high], end=" ")

# Driver Code
if __name__ == "__main__":

    arr = [4, 7, 3, 1, 3, 2, 5]
    n = len(arr)
    FirstGreater(arr, n)

    # This code is contributed by ukasp.
```

## C\#

```csharp
// C# code for the above approach
using System;

public class GFG
{
    static int upper_bound(int []arr, int N, int X)
    {
        int mid;

        // Initialise starting index and
        // ending index
        int low = 0;
        int high = N;

        // Till low is less than high
        while (low < high)
        {

            // Find the middle index
            mid = low + (high - low) / 2;

            // If X is greater than or equal
            // to arr[mid] then find
            // in right subarray
            if (X >= arr[mid]) {
                low = mid + 1;
            }

            // If X is less than arr[mid]
            // then find in left subarray
            else {
                high = mid;
            }
        }

        // if X is greater than arr[n-1]
        if (low < N && arr[low] <= X) {
            low++;
        }

        // Return the upper_bound index
        return low;
    }

    // Function to find first greater
    // element for every element of array
    static void FirstGreater(int []arr, int n)
    {

        // Creating copy array
        int []copy = new int[n];

        copy[0] = arr[0];
        for (int i = 1; i < n; i++)
        {

            // Updating element of copy[]
            copy[i] = Math.Max(copy[i - 1], arr[i]);
        }
        for (int i = 0; i < n; i++)
        {

            // High stores the index of first greater
            // for every element of []arr
            int high
                = upper_bound(copy, copy.Length, arr[i]);

            // If there no element
            // is greater than arr[i]
            // print -1
            if (high == n) {
                Console.Write("-1"
                             + " ");
            }

            // Otherwisw print the first element
            // which is greater than arr[i]
            else {
                Console.Write(arr[high] + " ");
            }
        }
    }

    // Driver Code
    public static void Main(String[] args)
    {
        int []arr = { 4, 7, 3, 1, 3, 2, 5 };
        int n = arr.Length;
        FirstGreater(arr, n);
    }
}

// This code is contributed by 29AjayKumar
```

## JavaScript

```javascript
// Javascript implementation of  the above approach

// Function to find first greater
// element for every element of array
function FirstGreater(arr, n) {

  // Creating copy array
  let copy = new Array(n);

  // Initializing all element of it with zero
  copy.fill(0)

  copy[0] = arr[0];

  for (let i = 1; i < n; i++) {

    // Updating element of copy[]
    copy[i] = Math.max(copy[i - 1], arr[i]);
  }

  for (let i = 0; i < n; i++) {

    // High stores the index of first greater
    // for every element of arr[]
    let high = upper_bound(copy, 0, copy.length - 1, arr[i]);

    // If there no element
    // is greater than arr[i]
    // print -1
    if (high == n) {
      document.write("-1 ");
    }

    // Otherwisw print the first element
    // which is greater than arr[i]
    else {
      document.write(arr[high] + " ");
    }
  }
}

function upper_bound(arr, low, high, X) {

  // Base Case
  if (low > high)
    return low;

  // Find the middle index
  let mid = Math.floor(low + (high - low) / 2);

  // If arr[mid] is less than
  // or equal to X search in
  // right subarray
  if (arr[mid] <= X) {
    return upper_bound(arr, mid + 1,
      high, X);
  }

  // If arr[mid] is greater than X
  // then search in left subarray
  return upper_bound(arr, low,
    mid - 1, X);
}

// Driver Code
let arr = [4, 7, 3, 1, 3, 2, 5];
let n = arr.length
FirstGreater(arr, n);

// This code is contributed by saurabh_jaiswal.
```

**Output**

```
7 -1 4 4 4 4 7 
```

时间复杂度: `O(n*log(n))`
辅助空间: `O(n)`