# 当数组不能修改时，数组中第K个最小元素使用常数空间

> 原文：[https://www.geeksforgeeks.org/kth-smallest-element-in-the-array-using-constant-space-when-array-cant-be-modified/](https://www.geeksforgeeks.org/kth-smallest-element-in-the-array-using-constant-space-when-array-cant-be-modified/)

给定一个大小为 `N` 的数组 `arr[]` 没有重复项，一个整数 `K`，任务是在恒定的额外空间中从数组中找到第 `K` 个最小元素，数组不能被修改。

**举例：**

> **输入：** `arr[] = {7, 10, 4, 3, 20, 15}`，`K = 3`
> **输出：** 7
> 排序后的给定数组是 `{3, 4, 7, 10, 15, 20}`，其中 7 是第三小元素。
> **输入：** `arr[] = {12, 3, 5, 7, 19}`，`K = 2`
> **输出：** 5

**进场：** 首先我们从阵中找到 `min` 和 `max` 元素。然后我们设置 `低 = min`、`高 = max` 和 `中 = (低 + 高) / 2`。
现在，执行修改后的二分搜索法，对于每个 `中` 我们计算小于 `中` 和等于 `中` 的元素数量。如果 `NumBer < k` 和 `NumBer + count equal >= k` 那么 `中` 就是我们的答案，否则我们就得修改我们的 `低` 和 `高`。
以下是上述方法的实施：

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function to return the kth smallest
// element from the array
int kthSmallest(int* arr, int k, int n)
{

    // Minimum and maximum element from the array
    int low = *min_element(arr, arr + n);
    int high = *max_element(arr, arr + n);

    // Modified binary search
    while (low <= high) {

        int mid = low + (high - low) / 2;

        // To store the count of elements from the array
        // which are less than mid and
        // the elements which are equal to mid
        int countless = 0, countequal = 0;
        for (int i = 0; i < n; ++i) {
            if (arr[i] < mid)
                ++countless;
            else if (arr[i] == mid)
                ++countequal;
        }

        // If mid is the kth smallest
        if (countless < k
            && (countless + countequal) >= k) {
            return mid;
        }

        // If the required element is less than mid
        else if (countless >= k) {
            high = mid - 1;
        }

        // If the required element is greater than mid
        else if (countless < k
                 && countless + countequal < k) {
            low = mid + 1;
        }
    }
}

// Driver code
int main()
{
    int arr[] = { 7, 10, 4, 3, 20, 15 };
    int n = sizeof(arr) / sizeof(int);
    int k = 3;

    cout << kthSmallest(arr, k, n);

    return 0;
}
```

## Java

```java
// Java implementation of the approach
import java.util.*;

class GFG
{

// Function to return the kth smallest
// element from the array
static int kthSmallest(int[] arr, int k, int n)
{

    // Minimum and maximum element from the array
    int low = Arrays.stream(arr).min().getAsInt();
    int high = Arrays.stream(arr).max().getAsInt();

    // Modified binary search
    while (low <= high)
    {

        int mid = low + (high - low) / 2;

        // To store the count of elements from the array
        // which are less than mid and
        // the elements which are equal to mid
        int countless = 0, countequal = 0;
        for (int i = 0; i < n; ++i)
        {
            if (arr[i] < mid)
                ++countless;
            else if (arr[i] == mid)
                ++countequal;
        }

        // If mid is the kth smallest
        if (countless < k
            && (countless + countequal) >= k)
        {
            return mid;
        }

        // If the required element is less than mid
        else if (countless >= k)
        {
            high = mid - 1;
        }

        // If the required element is greater than mid
        else if (countless < k
                && countless + countequal < k)
        {
            low = mid + 1;
        }
    }
    return Integer.MIN_VALUE;
}

// Driver code
public static void main(String[] args)
{
    int arr[] = { 7, 10, 4, 3, 20, 15 };
    int n = arr.length;
    int k = 3;

    System.out.println(kthSmallest(arr, k, n));
}
}

// This code is contributed by 29AjayKumar
```

## Python 3

```python
# Python3 implementation of the approach

# Function to return the kth smallest
# element from the array
def kthSmallest(arr, k, n) :

    # Minimum and maximum element from the array
    low = min(arr);
    high = max(arr);

    # Modified binary search
    while (low <= high) :

        mid = low + (high - low) // 2;

        # To store the count of elements from the array
        # which are less than mid and
        # the elements which are equal to mid
        countless = 0; countequal = 0;

        for i in range(n) :

            if (arr[i] < mid) :
                countless += 1;

            elif (arr[i] == mid) :
                countequal += 1;

        # If mid is the kth smallest
        if (countless < k and (countless + countequal) >= k) :
            return mid;

        # If the required element is less than mid
        elif (countless >= k) :
            high = mid - 1;

        # If the required element is greater than mid
        elif (countless < k and countless + countequal < k) :
            low = mid + 1;

# Driver code
if __name__ == "__main__" :

    arr = [ 7, 10, 4, 3, 20, 15 ];
    n = len(arr);
    k = 3;

    print(kthSmallest(arr, k, n));

# This code is contributed by AnkitRai01
```

## C#

```csharp
// C# implementation of the approach
using System;
using System.Linq;

class GFG
{

// Function to return the kth smallest
// element from the array
static int kthSmallest(int[] arr, int k, int n)
{

    // Minimum and maximum element from the array
    int low = arr.Min();
    int high = arr.Max();

    // Modified binary search
    while (low <= high)
    {

        int mid = low + (high - low) / 2;

        // To store the count of elements from the array
        // which are less than mid and
        // the elements which are equal to mid
        int countless = 0, countequal = 0;
        for (int i = 0; i < n; ++i)
        {
            if (arr[i] < mid)
                ++countless;
            else if (arr[i] == mid)
                ++countequal;
        }

        // If mid is the kth smallest
        if (countless < k
            && (countless + countequal) >= k)
        {
            return mid;
        }

        // If the required element is less than mid
        else if (countless >= k)
        {
            high = mid - 1;
        }

        // If the required element is greater than mid
        else if (countless < k
                && countless + countequal < k)
        {
            low = mid + 1;
        }
    }
    return int.MinValue;
}

// Driver code
public static void Main(String[] args)
{
    int []arr = { 7, 10, 4, 3, 20, 15 };
    int n = arr.Length;
    int k = 3;

    Console.WriteLine(kthSmallest(arr, k, n));
}
}

// This code is contributed by Rajput-Ji
```

## JavaScript 实现

```javascript
<script>

// JavaScript implementation of the approach

// Function to return the kth smallest
// element from the array
function kthSmallest(arr, k, n) {

    let temp = [...arr];
    // Minimum and maximum element from the array
    let low = temp.sort((a, b) => a - b)[0];
    let high = temp[temp.length - 1];

    // Modified binary search
    while (low <= high) {

        let mid = low + Math.floor((high - low) / 2);

        // To store the count of elements from the array
        // which are less than mid and
        // the elements which are equal to mid
        let countless = 0, countequal = 0;
        for (let i = 0; i < n; ++i) {
            if (arr[i] < mid)
                ++countless;
            else if (arr[i] == mid)
                ++countequal;
        }

        // If mid is the kth smallest
        if (countless < k
            && (countless + countequal) >= k) {
            return mid;
        }

        // If the required element is less than mid
        else if (countless >= k) {
            high = mid - 1;
        }

        // If the required element is greater than mid
        else if (countless < k
            && countless + countequal < k) {
            low = mid + 1;
        }
    }
}

// Driver code

let arr = [7, 10, 4, 3, 20, 15];
let n = arr.length;
let k = 3;

document.write(kthSmallest(arr, k, n));

// This code is contributed by gfgking

</script>
```

**Output:**

```

```

## 时间复杂度分析

**时间复杂度:** `O(N log(Max–Min))`，其中 `Max` 和 `Min` 分别是来自数组的最大和最小元素，`N` 是数组的大小。