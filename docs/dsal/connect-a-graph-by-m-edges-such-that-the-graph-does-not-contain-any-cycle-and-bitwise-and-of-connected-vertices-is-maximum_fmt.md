# 用 M 条边连接一个图，使得该图不包含任何循环，并且连接顶点的按位“与”最大

> 原文: [https://www.geeksforgeeks.org/connect-a-graph-by-m-edges-such-that-the-graph-does-not-contain-any-cycle-and-bitwise-and-of-connected-vertices-is-maximum/](https://www.geeksforgeeks.org/connect-a-graph-by-m-edges-such-that-the-graph-does-not-contain-any-cycle-and-bitwise-and-of-connected-vertices-is-maximum/)

给定一个由初始未连接的图的 `N` 个顶点的值和一个整数 `M` 组成的数组 `arr[]`，任务是将图的一些顶点与精确的 `M` 条边连接起来，只形成一个连通分量，这样就不会形成循环，并且最大化连接顶点的按位“与”值。

## 示例

**输入:** `arr[] = {1, 2, 3, 4}`，`M = 2`
**输出:** `0`
**解释:**
给定顶点之间 `M` 条边的以下排列为:
- `1->2->3` (`1 & 2 & 3 = 0`)。
- `2->3->4` (`2 & 3 & 4 = 0`)。
- `3->4->1` (`3 & 4 & 1 = 0`)。
- `1->2->4` (`1 & 2 & 4 = 0`)。

因此，所有情况中最大的按位“与”值为 `0`。

**输入:** `arr[] = {4, 5, 6}`，`M = 2`
**输出:** `4`
**解释:**
添加 `M` 条边的唯一可能方式是 `4->5->6` (`4 & 5 & 6 = 4`)。
因此，最大可能的按位“与”值为 `4`。

## 方法

解决给定问题的思路是使用 `M` 条边生成连接顶点的所有可能组合，并打印所有可能组合中的最大按位“与”值。

连接 `N` 个顶点的方式总数为 `2^N`，应该有 `(M + 1)` 个顶点，只构成一个连通分量。按照以下步骤解决给定的问题:

1.  初始化两个变量，将 `ans` 和 `mx` 设为 `0`，分别存储任意可能连通分量的节点的最大按位“与”和最终答案。
2.  使用变量 `i` 迭代范围 `[1, 2^N)`，并执行以下步骤:
    -   如果 `i` 有 `(M + 1)` 个置位，那么找到置位位置的按位“与”并存储在变量 `ans` 中。
    -   如果 `ans` 的值超过 `mx`，则更新 `mx` 的值为 `ans`。
3.  完成上述步骤后，将 `mx` 的值打印为最终最大按位“与”。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the maximum Bitwise
// AND of connected components possible
// by connecting a graph using M edges
int maximumAND(int arr[], int n, int m)
{
    // Stores total number of
    // ways to connect the graph
    int tot = 1 << n;

    // Stores the maximum Bitwise AND
    int mx = 0;

    // Iterate over the range [0, 2^n]
    for (int bm = 0; bm < tot; bm++) {
        // Store the Bitwise AND of
        // the connected vertices
        int andans = 0;

        // Store the count of the
        // connected vertices
        int count = 0;

        // Check for all the bits
        for (int i = 0; i < n; ++i) {
            // If i-th bit is set
            if ((bm >> i) & 1) {
                // If the first vertex is added
                if (count == 0) {
                    // Set andans equal to arr[i]
                    andans = arr[i];
                }
                else {
                    // Calculate Bitwise AND
                    // of arr[i] with andans
                    andans = andans & arr[i];
                }

                // Increase the count of
                // connected vertices
                count++;
            }
        }

        // If number of connected vertices
        // is (m + 1), no cycle is formed
        if (count == (m + 1)) {
            // Find the maximum Bitwise
            // AND value possible
            mx = max(mx, andans);
        }
    }

    // Return the maximum
    // Bitwise AND possible
    return mx;
}

// Driver Code
int main()
{
    int arr[] = { 1, 2, 3, 4 };
    int N = sizeof(arr) / sizeof(arr[0]);
    int M = 2;

    cout << maximumAND(arr, N, M);

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.util.*;

class GFG{

// Function to find the maximum Bitwise
// AND of connected components possible
// by connecting a graph using M edges
static int maximumAND(int arr[], int n, int m)
{

    // Stores total number of
    // ways to connect the graph
    int tot = 1 << n;

    // Stores the maximum Bitwise AND
    int mx = 0;

    // Iterate over the range [0, 2^n]
    for(int bm = 0; bm < tot; bm++)
    {

        // Store the Bitwise AND of
        // the connected vertices
        int andans = 0;

        // Store the count of the
        // connected vertices
        int count = 0;

        // Check for all the bits
        for(int i = 0; i < n; ++i)
        {

            // If i-th bit is set
            if (((bm >> i) & 1) != 0)
            {

                // If the first vertex is added
                if (count == 0)
                {

                    // Set andans equal to arr[i]
                    andans = arr[i];
                }
                else
                {

                    // Calculate Bitwise AND
                    // of arr[i] with andans
                    andans = andans & arr[i];
                }

                // Increase the count of
                // connected vertices
                count++;
            }
        }

        // If number of connected vertices
        // is (m + 1), no cycle is formed
        if (count == (m + 1))
        {

            // Find the maximum Bitwise
            // AND value possible
            mx = Math.max(mx, andans);
        }
    }

    // Return the maximum
    // Bitwise AND possible
    return mx;
}

// Driver Code
public static void main(String args[])
{
    int arr[] = { 1, 2, 3, 4 };
    int N = arr.length;
    int M = 2;

    System.out.println(maximumAND(arr, N, M));
}
}

// This code is contributed by souravghosh0416
```

## Python 3

```python
# Python3 program for the above approach

# Function to find the maximum Bitwise
# AND of connected components possible
# by connecting a graph using M edges
def maximumAND(arr, n, m):

    # Stores total number of
    # ways to connect the graph
    tot = 1 << n

    # Stores the maximum Bitwise AND
    mx = 0

    # Iterate over the range [0, 2^n]
    for bm in range(tot):

        # Store the Bitwise AND of
        # the connected vertices
        andans = 0

        # Store the count of the
        # connected vertices
        count = 0

        # Check for all the bits
        for i in range(n):

            # If i-th bit is set
            if ((bm >> i) & 1):

                # If the first vertex is added
                if (count == 0):

                    # Set andans equal to arr[i]
                    andans = arr[i]
                else:
                    # Calculate Bitwise AND
                    # of arr[i] with andans
                    andans = andans & arr[i]

                # Increase the count of
                # connected vertices
                count += 1

        # If number of connected vertices
        # is (m + 1), no cycle is formed
        if (count == (m + 1)):

            # Find the maximum Bitwise
            # AND value possible
            mx = max(mx, andans)

    # Return the maximum
    # Bitwise AND possible
    return mx

# Driver Code
if __name__ == '__main__':
    arr = [1, 2, 3, 4]
    N = len(arr)
    M = 2

    print (maximumAND(arr, N, M))

# This code is contributed by mohit kumar 29.
```

## C#

```
// C# program for the above approach
using System;

class GFG{

// Function to find the maximum Bitwise
// AND of connected components possible
// by connecting a graph using M edges
static int maximumAND(int[] arr, int n, int m)
{

    // Stores total number of
    // ways to connect the graph
    int tot = 1 << n;

    // Stores the maximum Bitwise AND
    int mx = 0;

    // Iterate over the range [0, 2^n]
    for(int bm = 0; bm < tot; bm++)
    {

        // Store the Bitwise AND of
        // the connected vertices
        int andans = 0;

        // Store the count of the
        // connected vertices
        int count = 0;

        // Check for all the bits
        for(int i = 0; i < n; ++i)
        {

            // If i-th bit is set
            if (((bm >> i) & 1) != 0 )
            {

                // If the first vertex is added
                if (count == 0)
                {

                    // Set andans equal to arr[i]
                    andans = arr[i];
                }
                else
                {

                    // Calculate Bitwise AND
                    // of arr[i] with andans
                    andans = andans & arr[i];
                }

                // Increase the count of
                // connected vertices
                count++;
            }
        }

        // If number of connected vertices
        // is (m + 1), no cycle is formed
        if (count == (m + 1))
        {

            // Find the maximum Bitwise
            // AND value possible
            mx = Math.Max(mx, andans);
        }
    }

    // Return the maximum
    // Bitwise AND possible
    return mx;
}

// Driver Code
static public void Main ()
{
    int[] arr = { 1, 2, 3, 4 };
    int N = arr.Length;
    int M = 2;

    Console.WriteLine(maximumAND(arr, N, M));
}
}

// This code is contributed by avanitrachhadiya2155
```

## JavaScript

```
<script>
// JavaScript program for the above approach

// Function to find the maximum Bitwise
// AND of connected components possible
// by connecting a graph using M edges
function maximumAND(arr, n, m)
{

    // Stores total number of
    // ways to connect the graph
    let tot = 1 << n;

    // Stores the maximum Bitwise AND
    let mx = 0;

    // Iterate over the range [0, 2^n]
    for(let bm = 0; bm < tot; bm++)
    {

        // Store the Bitwise AND of
        // the connected vertices
        let andans = 0;

        // Store the count of the
        // connected vertices
        let count = 0;

        // Check for all the bits
        for(let i = 0; i < n; ++i)
        {

            // If i-th bit is set
            if (((bm >> i) & 1) != 0)
            {

                // If the first vertex is added
                if (count == 0)
                {

                    // Set andans equal to arr[i]
                    andans = arr[i];
                }
                else
                {

                    // Calculate Bitwise AND
                    // of arr[i] with andans
                    andans = andans & arr[i];
                }

                // Increase the count of
                // connected vertices
                count++;
            }
        }

        // If number of connected vertices
        // is (m + 1), no cycle is formed
        if (count == (m + 1))
        {

            // Find the maximum Bitwise
            // AND value possible
            mx = Math.max(mx, andans);
        }
    }

    // Return the maximum
    // Bitwise AND possible
    return mx;
}

// Driver Code

    let arr = [ 1, 2, 3, 4 ];
    let N = arr.length;
    let M = 2;

    document.write(maximumAND(arr, N, M));

</script>
```

`Output:`

```
```

`时间复杂度:` O((2<sup>N</sup>)* N)
`辅助空间:` O(N)