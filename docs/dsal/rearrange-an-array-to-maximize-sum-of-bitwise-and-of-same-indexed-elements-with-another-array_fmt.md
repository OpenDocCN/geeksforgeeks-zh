# 重新排列一个数组，使相同索引元素与另一个数组的按位“与”之和最大化

> 原文: [https://www.geeksforgeeks.org/rearrange-an-array-to-maximize-sum-of-bitwise-and-of-same-indexed-elements-with-another-array/](https://www.geeksforgeeks.org/rearrange-an-array-to-maximize-sum-of-bitwise-and-of-same-indexed-elements-with-another-array/)

给定两个大小为 `N` 的[数组](https://www.geeksforgeeks.org/introduction-to-arrays/) `A[]` 和 `B[]`，任务是找出数组 `A[]` 和 `B[]` 中相同索引元素的[位与](https://www.geeksforgeeks.org/bitwise-operators-in-c-cpp/)的最大和，该和可以通过以任何顺序重新排列数组 `B[]` 来获得。

**示例:**

> **输入:** `A[] = {1，2，3，4}`，`B[] = {3，4，1，2}`
> **输出:** 10
> **解释:** 获得最大值的一种可能方法是将数组 `B[]` 重新排列为 `{1，2，3，4}`。
> 因此，数组 `A[]` 和 `B[]` 的同索引元素的按位 AND 之和= `{ 1&1+2&2+3&3+4&4 = 10 }`，这是最大可能。
>
> **输入:** `A[] = {3，5，7，11}`，`B[] = {2，6，10，12}`
> **输出:** 22

## 天真法

解决问题最简单的方法是[生成数组](https://www.geeksforgeeks.org/all-permutations-of-an-array-using-stl-in-c/) `B[]` 的所有可能排列，对于每个排列，计算数组 `A[]` 和 `B[]` 中相同索引元素的**位 AND** 之和，并相应更新最大可能和。最后，打印最大可能的总和。

**时间复杂度:** `O(N! * N)`
**辅助空间:** `O(1)`

## 高效方法

上述方法也可以基于以下观察进行优化:

*   对于数组 `A[]` 中的每个元素，思路是使用[位掩码](https://www.geeksforgeeks.org/bitmasking-and-dynamic-programming-set-1-count-ways-to-assign-unique-cap-to-every-person/)来选择数组 `B[]` 中未被选中的元素，这将为当前索引提供最大的按位 AND 和。
*   思路是使用[位掩码动态规划](https://www.geeksforgeeks.org/bitmasking-and-dynamic-programming-set-1-count-ways-to-assign-unique-cap-to-every-person/)，因为它具有多个[重叠子问题](https://www.geeksforgeeks.org/overlapping-subproblems-property-in-dynamic-programming-dp-1/)和[最优子结构](https://www.geeksforgeeks.org/optimal-substructure-property-in-dynamic-programming-dp-2/)。
*   假设 `DP(i, mask)` 表示数组 `A[]` 和索引 `i` 的最大位和，数组 `B[]` 中被选中的元素由 `mask` 的位位置表示。
*   那么从一个状态到另一个状态的转换可以定义为:
    *   对于范围 `[0, N]`:
        *   如果 `mask` 的第 `j` 位未被设置，`DP(i, mask) = max(dp(i, mask | (1 << j)))`

## 解决步骤

按照以下步骤解决问题:

*   用值 `-1` 定义一个维度为 `N * 2^N` 的[向量的向量](https://www.geeksforgeeks.org/vector-of-vectors-in-c-stl-with-examples/) `dp`，以存储所有 dp 状态。
*   定义一个[递归 DP 函数](https://www.geeksforgeeks.org/memoization-1d-2d-and-3d/)，比如 `maximizeUtil(i, mask)` 来求两个数组 `A[]` 和 `B[]` 中相同位置元素的按位 AND 的最大和:
    *   基本情况下，如果 `i` 等于 `N`，则返回 `0`。
    *   如果 `dp[i][mask]` 不等于 `-1`，即已经访问过，则返回 `dp[i][mask]`。
    *   使用变量 `j` 迭代范围 `[0, N-1]`，在每次迭代中，如果未设置掩码中的 `j` 第位，则将 `DP[i][mask]` 更新为 `DP[i][mask] = max(DP[i][mask], maximizeUtil(i+1, mask | 2^j))`。
    *   最后，返回 `dp[i][mask]`。
*   调用[递归函数](https://www.geeksforgeeks.org/recursive-functions/) `maximizeAnd(0, 0)` 并打印其返回值作为答案。

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to implement recursive DP
int maximizeAnd(int i, int mask,
                int* A, int* B, int N,
                vector<vector<int> >& dp)
{
    // If i is equal to N
    if (i == N)
        return 0;

    // If dp[i][mask] is not
    // equal to -1
    if (dp[i][mask] != -1)
        return dp[i][mask];

    // Iterate over the array B[]
    for (int j = 0; j < N; ++j) {

        // If current element
        // is not yet selected
        if (!(mask & (1 << j))) {

            // Update dp[i][mask]
            dp[i][mask] = max(
                dp[i][mask],
                (A[i] & B[j])
                    + maximizeAnd(i + 1, mask | (1 << j), A,
                                  B, N, dp));
        }
    }
    // Return dp[i][mask]
    return dp[i][mask];
}

// Function to obtain maximum sum
// of Bitwise AND of same-indexed
// elements from the arrays A[] and B[]
int maximizeAndUtil(int* A, int* B, int N)
{
    // Stores all dp-states
    vector<vector<int> > dp(
        N, vector<int>(1 << N + 1, -1));

    // Returns the maximum value
    // returned by the function maximizeAnd()
    return maximizeAnd(0, 0, A, B, N, dp);
}

// Driver Code
int main()
{
    int A[] = { 3, 5, 7, 11 };
    int B[] = { 2, 6, 10, 12 };
    int N = sizeof A / sizeof A[0];

    cout << maximizeAndUtil(A, B, N);
}
```

### Java

```java
// Java program for the above approach
import java.io.*;
import java.lang.*;
import java.util.*;

public class GFG {

    // Function to implement recursive DP
    static int maximizeAnd(int i, int mask, int A[],
                           int B[], int N, int[][] dp)
    {
        // If i is equal to N
        if (i == N)
            return 0;

        // If dp[i][mask] is not
        // equal to -1
        if (dp[i][mask] != -1)
            return dp[i][mask];

        // Iterate over the array B[]
        for (int j = 0; j < N; ++j) {

            // If current element
            // is not yet selected
            if ((mask & (1 << j)) == 0) {

                // Update dp[i][mask]
                dp[i][mask] = Math.max(
                    dp[i][mask],
                    (A[i] & B[j])
                        + maximizeAnd(i + 1,
                                      mask | (1 << j), A, B,
                                      N, dp));
            }
        }
        // Return dp[i][mask]
        return dp[i][mask];
    }

    // Function to obtain maximum sum
    // of Bitwise AND of same-indexed
    // elements from the arrays A[] and B[]
    static int maximizeAndUtil(int A[], int B[], int N)
    {

        // Stores all dp-states
        int dp[][] = new int[N][(1 << N) + 1];
        for (int dd[] : dp)
            Arrays.fill(dd, -1);

        // Returns the maximum value
        // returned by the function maximizeAnd()
        return maximizeAnd(0, 0, A, B, N, dp);
    }

    // Driver Code
    public static void main(String[] args)
    {
        int A[] = { 3, 5, 7, 11 };
        int B[] = { 2, 6, 10, 12 };
        int N = A.length;

        System.out.print(maximizeAndUtil(A, B, N));
    }
}

// This code is contributed by Kingash.
```

### Python3

```python
# Python3 program for the above approach

# Function to implement recursive DP
def maximizeAnd(i, mask, A, B, N, dp):

    # If i is equal to N
    if (i == N):
        return 0

    # If dp[i][mask] is not
    # equal to -1
    if (dp[i][mask] != -1):
        return dp[i][mask]

    # Iterate over the array B[]
    for j in range(N):

        # If current element
        # is not yet selected
        if ((mask & (1 << j)) == 0):

            # Update dp[i][mask]
            dp[i][mask] = max(
                dp[i][mask],(A[i] & B[j]) +
                maximizeAnd(i + 1, mask | (1 << j),
                            A, B, N, dp))

    # Return dp[i][mask]
    return dp[i][mask]

# Function to obtain maximum sum
# of Bitwise AND of same-indexed
# elements from the arrays A[] and B[]
def maximizeAndUtil(A, B, N):

    # Stores all dp-states
    temp = [-1 for i in range(1 << N + 1)]
    dp = [temp for i in range(N)]

    # Returns the maximum value
    # returned by the function maximizeAnd()
    return maximizeAnd(0, 0, A, B, N, dp)

# Driver Code
if __name__ == '__main__':

    A = [ 3, 5, 7, 11 ]
    B = [ 2, 6, 10, 12 ]
    N = len(A)

    print(maximizeAndUtil(A, B, N))

# This code is contributed by ipg2016107
```

## `C#`

```
// C# program for the above approach
using System;

class GFG {

    // Function to implement recursive DP
    static int maximizeAnd(int i, int mask, int[] A,
                           int[] B, int N, int[,] dp)
    {
        // If i is equal to N
        if (i == N)
            return 0;

        // If dp[i][mask] is not
        // equal to -1
        if (dp[i, mask] != -1)
            return dp[i, mask];

        // Iterate over the array B[]
        for (int j = 0; j < N; ++j) {

            // If current element
            // is not yet selected
            if ((mask & (1 << j)) == 0) {

                // Update dp[i][mask]
                dp[i, mask] = Math.Max(
                    dp[i, mask],
                    (A[i] & B[j])
                        + maximizeAnd(i + 1,
                                      mask | (1 << j), A, B,
                                      N, dp));
            }
        }
        // Return dp[i][mask]
        return dp[i, mask];
    }

    // Function to obtain maximum sum
    // of Bitwise AND of same-indexed
    // elements from the arrays A[] and B[]
    static int maximizeAndUtil(int[] A, int[] B, int N)
    {

        // Stores all dp-states
        int[,] dp = new int[N, (1 << N) + 1];
        for(int i = 0; i<N; i++)
        {
            for(int j =0 ; j<(1 << N) + 1; j++)
            {
                dp[i, j] = -1;
            }
        }

        // Returns the maximum value
        // returned by the function maximizeAnd()
        return maximizeAnd(0, 0, A, B, N, dp);
    }

    // Driver Code
    static void Main()
    {
        int[] A = { 3, 5, 7, 11 };
        int[] B = { 2, 6, 10, 12 };
        int N = A.Length;

        Console.Write(maximizeAndUtil(A, B, N));
    }
}

// This code is contributed by sanjoy_62.
```

## `java 描述语言`

```
<script>

// Javascript program for the above approach

// Function to implement recursive DP
function maximizeAnd(i, mask, A, B, N, dp)
{

    // If i is equal to N
    if (i == N)
        return 0;

    // If dp[i][mask] is not
    // equal to -1
    if (dp[i][mask] != -1)
        return dp[i][mask];

    // Iterate over the array B[]
    for(var j = 0; j < N; ++j)
    {

        // If current element
        // is not yet selected
        if (!(mask & (1 << j)))
        {

            // Update dp[i][mask]
            dp[i][mask] = Math.max(
                dp[i][mask], (A[i] & B[j]) +
                maximizeAnd(i + 1, mask | (1 << j), A,
                            B, N, dp));
        }
    }

    // Return dp[i][mask]
    return dp[i][mask];
}

// Function to obtain maximum sum
// of Bitwise AND of same-indexed
// elements from the arrays A[] and B[]
function maximizeAndUtil(A, B, N)
{

    // Stores all dp-states
    var dp = Array.from(
        Array(N), () => Array(1 << N + 1).fill(-1));

    // Returns the maximum value
    // returned by the function maximizeAnd()
    return maximizeAnd(0, 0, A, B, N, dp);
}

// Driver Code
var A = [ 3, 5, 7, 11 ];
var B = [ 2, 6, 10, 12 ];
var N = A.length

document.write(maximizeAndUtil(A, B, N));

// This code is contributed by rrrtnx

</script>
```

`Output:`

```

```

`时间复杂度:` O(N<sup>2</sup>* 2<sup>N)</sup>
`辅助空间:` O(N * 2 <sup>N</sup>