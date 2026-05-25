# 将数组拆分成最小数量的子集，子集的最大对和最多为 K

> 原文: [https://www.geeksforgeeks.org/split-array-into-minimum-number-of-subsets-having-maximum-pair-sum-at-most-k/](https://www.geeksforgeeks.org/split-array-into-minimum-number-of-subsets-having-maximum-pair-sum-at-most-k/)

## 问题描述

给定一个大小为 `N` 的数组 `arr[]` 和一个整数 `K`，任务是将数组划分为最小数量的子集，使得每个子集内的最大对和小于或等于 `K`。

### 示例

> **输入:** `arr[] = {1, 2, 3, 4, 5}`，`K = 5`
> **输出:** 3
> **解释:**
> 最大对和小于或等于 `K(= 5)` 的子集为: `{{2, 3}, {1, 4}, {5}}`。
> 因此，要求的输出为 3。

> **输入:** `arr[] = {2, 6, 8, 10, 20, 25}`，`K = 26`
> **输出:** 3
> **解释:**
> 最大对和小于或等于 `K(=26)` 的子集为: `{{2, 6, 8, 10}, {20}, {25}}`。
> 因此，要求的输出为 3。

## 方法

使用双指针技术可以解决问题。其思想是对数组进行分区，使得每个子集的最大对和最小。按照以下步骤解决问题:

*   给定数组排序。
*   初始化一个变量，比如 `res` 来存储满足给定条件的子集的最小数量。
*   初始化两个变量，说 `开始` 和 `结束` 分别存储排序数组的开始和结束索引。
*   遍历排序后的数组，检查 `arr[开始] + arr[结束] ≤ K`。如果发现为真，则将 `开始` 的值增加 `1`。
*   否则，以 `1` 递减 `结束` 的值，以 `1` 递增 `开始`。
*   最后，打印 `res` 的值。

下面是上述方法的实现:

### C++

```cpp
// C++ program to implement
// the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to get the minimum
// count of subsets that satisfy
// the given condition
int cntMinSub(int arr[],
              int N, int K)
{
    // Store the minimum count
    // of subsets that satisfy
    // the given condition
    int res = 0;

    // Stores start index
    // of the sorted array.
    int start = 0;

    // Stores end index
    // of the sorted array
    int end = N - 1;

    // Sort the given array
    sort(arr, arr + N);

    // Traverse the array
    while (end - start > 1) {
        if (arr[start] + arr[end]
            <= K) {
            start++;
        }
        else {
            res++;
            end--;
        }
    }

    // If only two elements
    // of sorted array left
    if (end - start == 1) {
        if (arr[start] + arr[end]
            <= K) {
            res++;
            start++;
            end--;
        }
        else {
            res++;
            end--;
        }
    }

    // If only one elements
    // left in the array
    if (start == end) {
        res++;
    }

    return res;
}

// Driver Code
int main()
{
    int arr[] = { 2, 6, 8, 10, 20, 25 };
    int N = sizeof(arr) / sizeof(arr[0]);
    int K = 26;
    cout << cntMinSub(arr, N, K);
}
```

### Java

```java
// Java program to implement
// the above approach
import java.util.*;
class GFG{

// Function to get the minimum
// count of subsets that satisfy
// the given condition
static int cntMinSub(int arr[],
                     int N, int K)
{
  // Store the minimum count
  // of subsets that satisfy
  // the given condition
  int res = 0;

  // Stores start index
  // of the sorted array.
  int start = 0;

  // Stores end index
  // of the sorted array
  int end = N - 1;

  // Sort the given array
  Arrays.sort(arr);

  // Traverse the array
  while (end - start > 1)
  {
    if (arr[start] +
        arr[end] <= K)
    {
      start++;
    }
    else
    {
      res++;
      end--;
    }
  }

  // If only two elements
  // of sorted array left
  if (end - start == 1)
  {
    if (arr[start] +
        arr[end] <= K)
    {
      res++;
      start++;
      end--;
    }
    else
    {
      res++;
      end--;
    }
  }

  // If only one elements
  // left in the array
  if (start == end)
  {
    res++;
  }

  return res;
}

// Driver Code
public static void main(String[] args)
{
  int arr[] = {2, 6, 8, 10, 20, 25};
  int N = arr.length;
  int K = 26;
  System.out.print(cntMinSub(arr, N, K));
}
}

// This code is contributed by shikhasingrajput
```

### Python 3

```python
# Python3 program to implement
# the above approach

# Function to get the minimum
# count of subsets that satisfy
# the given condition
def cntMinSub(arr, N, K):

    # Store the minimum count
    # of subsets that satisfy
    # the given condition
    res = 0

    # Stores start index
    # of the sorted array.
    start = 0

    # Stores end index
    # of the sorted array
    end = N - 1

    # Sort the given array
    arr = sorted(arr)

    # Traverse the array
    while (end - start > 1):
        if (arr[start] + arr[end] <= K):
            start += 1
        else:
            res += 1
            end -= 1

    # If only two elements
    # of sorted array left
    if (end - start == 1):
        if (arr[start] + arr[end] <= K):
            res += 1
            start += 1
            end -= 1
        else:
            res += 1
            end -= 1

    # If only one elements
    # left in the array
    if (start == end):
        res += 1

    return res

# Driver Code
if __name__ == '__main__':

    arr = [ 2, 6, 8, 10, 20, 25 ]
    N = len(arr)
    K = 26

    print(cntMinSub(arr, N, K))

# This code is contributed by mohit kumar 29
```

### C#

```csharp
// C# program to implement
// the above approach
using System;
class GFG{

// Function to get the minimum
// count of subsets that satisfy
// the given condition
static int cntMinSub(int []arr,
                     int N, int K)
{
  // Store the minimum count
  // of subsets that satisfy
  // the given condition
  int res = 0;

  // Stores start index
  // of the sorted array.
  int start = 0;

  // Stores end index
  // of the sorted array
  int end = N - 1;

  // Sort the given array
  Array.Sort(arr);

  // Traverse the array
  while (end - start > 1)
  {
    if (arr[start] +
        arr[end] <= K)
    {
      start++;
    }
    else
    {
      res++;
      end--;
    }
  }

  // If only two elements
  // of sorted array left
  if (end - start == 1)
  {
    if (arr[start] +
        arr[end] <= K)
    {
      res++;
      start++;
      end--;
    }
    else
    {
      res++;
      end--;
    }
  }

  // If only one elements
  // left in the array
  if (start == end)
  {
    res++;
  }

  return res;
}

// Driver Code
public static void Main(String[] args)
{
  int []arr = {2, 6, 8, 10, 20, 25};
  int N = arr.Length;
  int K = 26;
  Console.Write(cntMinSub(arr, N, K));
}
}

// This code is contributed by 29AjayKumar
```

### JavaScript

```javascript
<script>

// Javascript program to implement
// the above approach

// Function to get the minimum
// count of subsets that satisfy
// the given condition
function cntMinSub(arr, N, K)
{

    // Store the minimum count
    // of subsets that satisfy
    // the given condition
    var res = 0;

    // Stores start index
    // of the sorted array.
    var start = 0;

    // Stores end index
    // of the sorted array
    var end = N - 1;

    // Sort the given array
    arr.sort();

    // Traverse the array
    while (end - start > 1)
    {
        if (arr[start] + arr[end] <= K)
        {
            start++;
        }
        else
        {
            res++;
            end--;
        }
    }

    // If only two elements
    // of sorted array left
    if (end - start == 1)
    {
        if (arr[start] + arr[end] <= K)
        {
            res++;
            start++;
            end--;
        }
        else
        {
            res++;
            end--;
        }
    }

    // If only one elements
    // left in the array
    if (start == end)
    {
        res++;
    }

    return res;
}

// Driver Code
var arr = [ 2, 6, 8, 10, 20, 25 ];
var N = arr.length;
var K = 26;

document.write(cntMinSub(arr, N, K));

// This code is contributed by gauravrajput1

</script>
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`