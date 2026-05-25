# 在一个数组中能够替换全 1 的最小数，使得任意一对相邻元素之间的最大绝对差最小

> 原文:[https://www . geesforgeks . org/可以替换数组中所有 1 的最小数字，使得任意相邻元素对之间的最大绝对差值最小/](https://www.geeksforgeeks.org/smallest-number-that-can-replace-all-1s-in-an-array-such-that-maximum-absolute-difference-between-any-pair-of-adjacent-elements-is-minimum/)

## 问题描述

给定一个由 `N` 个正整数和一些值为 `-1` 的元素组成的数组 `arr[]`，任务是找到最小的数，比如说 `K`，这样用 `K` 替换数组中的所有 `-1` 就可以使任意一对相邻元素之间的最大绝对差最小化。

## 示例

> **输入:** `arr[] = {-1，10，-1，12，-1}`
> **输出:** `11`
> **说明:**
> 把 `K` 的值考虑为 `11`。现在，将值为 `-1` 的所有数组元素替换为值 `K`(= `11`)会将数组修改为 `{11，10，11，12，11}`。所有相邻元素之间的最大绝对差是 `1`，这是所有可能的 `k` 值中的最小值
>
> **输入:** `arr[] = {1，-1，3，-1}`
> **输出:** `2`

## 天真方法

解决给定问题的最简单方法是迭代来自 `1` 的 `K` 的所有可能值，逐一检查 `K` 的哪个值给出了任意两个相邻元素之间的最小化最大绝对差，并打印该值 `K`。

**时间复杂度:** `O(N*K)`
**辅助空间:** `O(1)`

## 高效方法

上述方法也可以基于以下观察进行优化:

*   如果任何数字的绝对值，比如说 `X` 要从数字的集合中最小化，则集合的最小和最大元素的平均值是使绝对值最小化的 `X` 的最优值。
*   因此，其思想是找出与元素 `-1` 相邻的所有数组元素的最小值和最大值，并将两个数的平均值打印为 `K` 的合成值。

按照以下步骤解决问题:

*   初始化两个变量，说 `maxE` 为 `INT_MIN` 和 `minE` 为 `INT_MAX`，以存储数组中与 `-1` 相邻的所有可能值中的最大和最小元素。
*   遍历给定数组并执行以下步骤:
    *   如果当前元素 `arr[i]` 为 `-1`，下一个元素不是 `-1`，则将 `maxE` 的值更新为 `maxE` 和 `arr[i+1]` 的最大值，`minE` 更新为 `minE` 和 `arr[i+1]` 的最小值。
    *   如果当前元素 `arr[i]` 不是 `-1`，下一个元素是 `-1`，则将 `maxE` 的值更新为 `maxE` 和 `arr[i]` 的最大值，`minE` 更新为 `minE` 和 `arr[i]` 的最小值。
*   完成上述步骤后，如果 `maxE` 和 `minE` 的值不变，则所有数组元素都为 `-1`，因此，打印 `0` 作为 `K` 的合成值。否则，打印 `minE` 和 `maxE` 的平均值作为 `K` 的合成值。

## 代码实现

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to find the value of K to
// minimize the value of maximum absolute
// difference between adjacent elements
void findMissingValue(int arr[], int N)
{

    // Stores the maximum and minimum
    // among array elements that are
    // adjacent to "-1"
    int minE = INT_MAX, maxE = INT_MIN;

    // Traverse the given array arr[]
    for (int i = 0; i < N - 1; i++) {

        // If arr[i] is -1 & arr[i + 1]
        // is not -1
        if (arr[i] == -1
            && arr[i + 1] != -1) {
            minE = min(minE, arr[i + 1]);
            maxE = max(maxE, arr[i + 1]);
        }

        // If arr[i + 1] is -1 & arr[i]
        // is not -1
        if (arr[i] != -1
            && arr[i + 1] == -1) {
            minE = min(minE, arr[i]);
            maxE = max(maxE, arr[i]);
        }
    }

    // If all array element is -1
    if (minE == INT_MAX
        and maxE == INT_MIN) {
        cout << "0";
    }

    // Otherwise
    else {
        cout << (minE + maxE) / 2;
    }
}

// Driver Code
int main()
{
    int arr[] = { 1, -1, -1, -1, 5 };
    int N = sizeof(arr) / sizeof(arr[0]);
    findMissingValue(arr, N);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.io.*;

class GFG{

// Function to find the value of K to
// minimize the value of maximum absolute
// difference between adjacent elements
public static void findMissingValue(int arr[], int N)
{

    // Stores the maximum and minimum
    // among array elements that are
    // adjacent to "-1"
    int minE = Integer.MAX_VALUE,
        maxE = Integer.MIN_VALUE;

    // Traverse the given array arr[]
    for(int i = 0; i < N - 1; i++)
    {

        // If arr[i] is -1 & arr[i + 1]
        // is not -1
        if (arr[i] == -1 && arr[i + 1] != -1)
        {
            minE = Math.min(minE, arr[i + 1]);
            maxE = Math.max(maxE, arr[i + 1]);
        }

        // If arr[i + 1] is -1 & arr[i]
        // is not -1
        if (arr[i] != -1 && arr[i + 1] == -1)
        {
            minE = Math.min(minE, arr[i]);
            maxE = Math.max(maxE, arr[i]);
        }
    }

    // If all array element is -1
    if (minE == Integer.MAX_VALUE &&
        maxE == Integer.MIN_VALUE)
    {
        System.out.println("0");
    }

    // Otherwise
    else
    {
        System.out.println((minE + maxE) / 2);
    }
}

// Driver Code
public static void main(String[] args)
{
    int arr[] = { 1, -1, -1, -1, 5 };
    int N = arr.length;

    findMissingValue(arr, N);
}
}

// This code is contributed by Potta Lokesh
```

### Python 3

```python
# Python 3 program for the above approach
import sys

# Function to find the value of K to
# minimize the value of maximum absolute
# difference between adjacent elements
def findMissingValue(arr, N):

    # Stores the maximum and minimum
    # among array elements that are
    # adjacent to "-1"
    minE = sys.maxsize
    maxE = -sys.maxsize - 1

    # Traverse the given array arr[]
    for i in range(N - 1):

        # If arr[i] is -1 & arr[i + 1]
        # is not -1
        if (arr[i] == -1 and arr[i + 1] != -1):
            minE = min(minE, arr[i + 1])
            maxE = max(maxE, arr[i + 1])

        # If arr[i + 1] is -1 & arr[i]
        # is not -1
        if (arr[i] != -1 and arr[i + 1] == -1):
            minE = min(minE, arr[i])
            maxE = max(maxE, arr[i])

    # If all array element is -1
    if (minE == sys.maxsize and maxE == -sys.maxsize-1):
        print("0")

    # Otherwise
    else:
        print((minE + maxE) // 2)

# Driver Code
if __name__ == '__main__':
    arr = [1, -1, -1, -1, 5]
    N = len(arr)
    findMissingValue(arr, N)

    # This code is contributed by SURENDRA_GANGWAR.
```

### C\#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to find the value of K to
// minimize the value of maximum absolute
// difference between adjacent elements
public static void findMissingValue(int[] arr, int N)
{

    // Stores the maximum and minimum
    // among array elements that are
    // adjacent to "-1"
    int minE = Int32.MaxValue,
        maxE = Int32.MinValue;

    // Traverse the given array arr[]
    for(int i = 0; i < N - 1; i++)
    {

        // If arr[i] is -1 & arr[i + 1]
        // is not -1
        if (arr[i] == -1 && arr[i + 1] != -1)
        {
            minE = Math.Min(minE, arr[i + 1]);
            maxE = Math.Max(maxE, arr[i + 1]);
        }

        // If arr[i + 1] is -1 & arr[i]
        // is not -1
        if (arr[i] != -1 && arr[i + 1] == -1)
        {
            minE = Math.Min(minE, arr[i]);
            maxE = Math.Max(maxE, arr[i]);
        }
    }

    // If all array element is -1
    if (minE == Int32.MaxValue &&
        maxE == Int32.MinValue)
    {
        Console.WriteLine("0");
    }

    // Otherwise
    else
    {
        Console.WriteLine((minE + maxE) / 2);
    }
}

// Driver Code
public static void Main()
{
    int[] arr = { 1, -1, -1, -1, 5 };
    int N = arr.Length;

    findMissingValue(arr, N);
}
}

// This code is contributed by rishavmahato348
```

# JavaScript 实现

## 代码实现

```javascript
<script>

// JavaScript program for the above approach

// Function to find the value of K to
// minimize the value of maximum absolute
// difference between adjacent elements
function findMissingValue(arr, N)
{

    // Stores the maximum and minimum
    // among array elements that are
    // adjacent to "-1"
    let minE = Number.MAX_VALUE,
        maxE = Number.MIN_VALUE;

    // Traverse the given array arr[]
    for(let i = 0; i < N - 1; i++)
    {

        // If arr[i] is -1 & arr[i + 1]
        // is not -1
        if (arr[i] == -1 && arr[i + 1] != -1)
        {
            minE = Math.min(minE, arr[i + 1]);
            maxE = Math.max(maxE, arr[i + 1]);
        }

        // If arr[i + 1] is -1 & arr[i]
        // is not -1
        if (arr[i] != -1 && arr[i + 1] == -1)
        {
            minE = Math.min(minE, arr[i]);
            maxE = Math.max(maxE, arr[i]);
        }
    }

    // If all array element is -1
    if (minE == Number.MAX_VALUE &&
        maxE == Number.MIN_VALUE)
    {
        document.write("0");
    }

    // Otherwise
    else
    {
        document.write((minE + maxE) / 2);
    }
}

// Driver Code
let arr = [ 1, -1, -1, -1, 5 ];
let N = arr.length;

findMissingValue(arr, N);

// This code is contributed by Potta Lokesh

</script>
```

**Output:**

```

```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`