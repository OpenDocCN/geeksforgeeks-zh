# 未排序数组中最接近 K 的值

> 原文: [https://www.geeksforgeeks.org/closest-value-to-k-from-an-unsorted-array/](https://www.geeksforgeeks.org/closest-value-to-k-from-an-unsorted-array/)

给定一个由 `N` 个整数和一个整数 `K` 组成的数组 `arr[]`，任务是找到最接近 `K` 的数组元素。如果存在多个最接近的值，则打印最小的值。

**示例:**

> **输入:** `arr[]={4, 2, 8, 11, 7}`，`K = 6`
> **输出:** `7`
> **解释:**
> `4` 和 `6` 的绝对差为 `|4–6| = 2`
> `2` 和 `6` 的绝对差为 `|2–6| = 4`
> `8` 和 `6` 的绝对差为 `|8–6| = 2`
> `11` 和 `6` 的绝对差为 `|11–6| = 5`
> 因此，`K(=6)` 的最接近值是 `7`
>
> **输入:** `arr[]={100, 200, 400}`，`K = 300`
> **输出:** `200`

## 方法

思路是遍历给定数组并打印出与给定整数 `K` 的绝对差最小的数组元素。按照以下步骤解决问题:

1.  初始化一个变量，比如说 `res`，将数组元素存储为最接近 `K` 的值。
2.  遍历数组，比较 `abs(K - res)` 的绝对值和 `abs(K - arr[i])` 的绝对值。
3.  如果 `abs(K - res)` 的值超过 `abs(K - arr[i])`，则更新 `res` 为 `arr[i]`。
4.  最后，打印 `res`。

下面是上述方法的实现:

### C++

```cpp
// C++ program to implement
// the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to get
// the closest value
int clostVal(int arr[],
             int N,
             int K)
{
    // Stores the closest
    // value to K
    int res = arr[0];

    // Traverse the array
    for (int i = 1; i < N;
         i++) {

        // If absolute difference
        // of K and res exceeds
        // absolute difference of K
        // and current element
        if (abs(K - res) > abs(K - arr[i])) {
            res = arr[i];
        }
    }

    // Return the closest
    // array element
    return res;
}

// Driver Code
int main()
{
    int arr[] = { 100, 200, 400 };
    int K = 300;
    int N = sizeof(arr) / sizeof(arr[0]);

    cout << clostVal(arr, N, K);
}
```

### Java

```java
// Java program to implement
// the above approach
import java.io.*;

class GFG{

// Function to get
// the closest value
static int clostVal(int arr[], int N,
                    int K)
{

    // Stores the closest
    // value to K
    int res = arr[0];

    // Traverse the array
    for(int i = 1; i < N; i++)
    {

        // If absolute difference
        // of K and res exceeds
        // absolute difference of K
        // and current element
        if (Math.abs(K - res) >
            Math.abs(K - arr[i]))
        {
            res = arr[i];
        }
    }

    // Return the closest
    // array element
    return res;
}

// Driver Code
public static void main (String[] args)
{
    int arr[] = { 100, 200, 400 };
    int K = 300;
    int N = arr.length;

    System.out.print(clostVal(arr, N, K));
}
}

// This code is contributed by code_hunt
```

### Python 3

```python
# Python3 program to implement
# the above approach

# Function to get
# the closest value
def clostVal(arr, N, K):

    # Stores the closest
    # value to K
    res = arr[0]

    # Traverse the array
    for i in range(1, N, 1):

        # If absolute difference
        # of K and res exceeds
        # absolute difference of K
        # and current element
        if (abs(K - res) >
            abs(K - arr[i])):
            res = arr[i]

    # Return the closest
    # array element
    return res

# Driver Code
arr = [ 100, 200, 400 ]
K = 300
N = len(arr)

print(clostVal(arr, N, K))

# This code is contributed by susmitakundugoaldanga
```

### C#

```csharp
// C# program to implement
// the above approach
using System;

class GFG{

// Function to get
// the closest value
static int clostVal(int[] arr, int N,
                    int K)
{

    // Stores the closest
    // value to K
    int res = arr[0];

    // Traverse the array
    for(int i = 1; i < N; i++)
    {

        // If absolute difference
        // of K and res exceeds
        // absolute difference of K
        // and current element
        if (Math.Abs(K - res) >
            Math.Abs(K - arr[i]))
        {
            res = arr[i];
        }
    }

    // Return the closest
    // array element
    return res;
}

// Driver Code
public static void Main ()
{
    int[] arr = { 100, 200, 400 };
    int K = 300;
    int N = arr.Length;

    Console.WriteLine(clostVal(arr, N, K));
}
}

// This code is contributed by sanjoy_62
```

### JavaScript

```javascript
<script>

// Javascript program to implement
// the above approach

// Function to get
// the closest value
function clostVal(arr, N, K)
{

    // Stores the closest
    // value to K
    let res = arr[0];

    // Traverse the array
    for(let i = 1; i < N; i++)
    {

        // If absolute difference
        // of K and res exceeds
        // absolute difference of K
        // and current element
        if (Math.abs(K - res) >
            Math.abs(K - arr[i]))
        {
            res = arr[i];
        }
    }

    // Return the closest
    // array element
    return res;
}

// Driver Code

    let arr = [ 100, 200, 400 ];
    let K = 300;
    let N = arr.length;

    document.write(clostVal(arr, N, K));

</script>
```

**输出:**

```
200
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`