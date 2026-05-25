# 用它们的乘积替换相邻对可以得到的最小数组

> 原文: [https://www.geeksforgeeks.org/smallest-array-that-can-be-obtained-by-replacing-adjacent-pairs-with-their-products/](https://www.geeksforgeeks.org/smallest-array-that-can-be-obtained-by-replacing-adjacent-pairs-with-their-products/)

## 问题描述

给定大小为 `N` 的数组 `arr[]`，任务是通过执行以下操作来打印给定数组可以缩小到的最小可能大小：

*   移除任意两个相邻的元素，比如 `arr[i]` 和 `arr[i+1]`，并在数组中的该位置插入单个元素 `arr[i] * arr[i+1]`。
*   如果所有数组元素相等，则打印数组的大小。

## 示例

**输入:** `arr[] = {1, 7, 7, 1, 7, 1}`
**输出:** 1
**解释:**
选择 `arr[0]` 和 `arr[1]` 并替换为 `arr[0]*arr[1]`，`arr[] = {7, 7, 1, 7, 1}`
选择 `arr[0]` 和 `arr[1]` 并替换为 `arr[0]*arr[1]`，`arr[] = {49, 1, 7, 1}`

**输入:** `arr[] = {2, 2, 2, 2}`
**输出:** 4

## 方法

该方法基于这样的思想：如果所有数组元素都相同，那么给定的操作就不能在给定的数组上执行。否则，在任何情况下，数组大小都可以减少到 1。以下是步骤：

1.  迭代给定的数组 `arr[]`。
2.  如果数组的所有元素都相同，则打印 `N` 作为所需答案。
3.  否则，总是选择给出最大乘积的相邻元素，以将 `arr[]` 的大小减少到 1。因此，最小可能尺寸为 1。

下面是上述方法的实现：

## C++

```cpp
// C++ implementation of the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to minimize the size of
// array by performing given operations
int minLength(int arr[], int N)
{

    for (int i = 1; i < N; i++) {

        // If all array elements
        // are not same
        if (arr[0] != arr[i]) {
            return 1;
        }
    }

    // If all array elements
    // are same
    return N;
}

// Driver Code
int main()
{
    int arr[] = { 2, 1, 3, 1 };
    int N = sizeof(arr) / sizeof(arr[0]);

    // Function Call
    cout << minLength(arr, N);

    return 0;
}
```

## Java

```java
// Java implementation of the above approach
import java.io.*;

class GFG{

// Function to minimize the size of
// array by performing given operations
static int minLength(int arr[], int N)
{
    for(int i = 1; i < N; i++)
    {

        // If all array elements
        // are not same
        if (arr[0] != arr[i])
        {
            return 1;
        }
    }

    // If all array elements
    // are same
    return N;
}

// Driver Code
public static void main(String[] args)
{
    int[] arr = { 2, 1, 3, 1 };
    int N = arr.length;

    // Function call
    System.out.print(minLength(arr, N));
}
}

// This code is contributed by akhilsaini
```

## Python 3

```python
# Python3 implementation of the above approach

# Function to minimize the size of
# array by performing given operations
def minLength(arr, N):

    for i in range(1, N):

        # If all array elements
        # are not same
        if (arr[0] != arr[i]):
            return 1

    # If all array elements
    # are same
    return N

# Driver Code
if __name__ == "__main__":

    arr = [ 2, 1, 3, 1 ]
    N = len(arr)

    # Function call
    print(minLength(arr, N))

# This code is contributed by akhilsaini
```

## C#

```csharp
// C# implementation of the above approach
using System;

class GFG{

// Function to minimize the size of
// array by performing given operations
static int minLength(int[] arr, int N)
{
    for(int i = 1; i < N; i++)
    {

        // If all array elements
        // are not same
        if (arr[0] != arr[i])
        {
            return 1;
        }
    }

    // If all array elements
    // are same
    return N;
}

// Driver Code
public static void Main()
{
    int[] arr = { 2, 1, 3, 1 };
    int N = arr.Length;

    // Function call
    Console.Write(minLength(arr, N));
}
}

// This code is contributed by akhilsaini
```

## JavaScript

```javascript
<script>

// Javascript program to implement
// the above approach

// Function to minimize the size of
// array by performing given operations
function minLength(arr, N)
{
    for(let i = 1; i < N; i++)
    {

        // If all array elements
        // are not same
        if (arr[0] != arr[i])
        {
            return 1;
        }
    }

    // If all array elements
    // are same
    return N;
}

// Driver Code

    let arr = [ 2, 1, 3, 1 ];
    let N = arr.length;

    // Function call
    document.write(minLength(arr, N));

</script>
```

**Output:**

```
1
```

## 复杂度分析

*   **时间复杂度:** `O(N)`
*   **辅助空间:** `O(1)`