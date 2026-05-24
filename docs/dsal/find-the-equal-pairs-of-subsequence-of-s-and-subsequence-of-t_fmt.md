# 求 S 的子序列和 T 的子序列的等对

> 原文：[https://www.geeksforgeeks.org/find-the-equal-pairs-of-subsequence-of-s-and-subsequence-of-t/](https://www.geeksforgeeks.org/find-the-equal-pairs-of-subsequence-of-s-and-subsequence-of-t/)

## 问题描述

给定两个数组 `S[]` 和 `T[]`，大小分别为 `N` 和 `M`。任务是找到内容相同的 `S[]` 的子序列对和 `T[]` 的子序列对。答案可能非常大。所以，打印答案模 `10^9 + 7`。

## 示例

**输入：** `S[] = {1，1}`，`T[] = {1，1}`
**输出：** 6
`S[]`的子序列为`{}`、`{1}`、`{1}`和`{1，1}`。
`T[]`的子序列是`{}`、`{1}`、`{1}`和`{1，1}`。
所有有效的对是(`{}`，`{}`)、(`{1}`，`{1}`)、(`{1}`，`{1}`)、(`{1}`，`{1}`)、(`{1}`，`{1}`)和(`{1，1}`，`{1，1}`)。

**输入：** `S[] = {1，3}`，`T[] = {3，1}`
**输出：** 3

## 方法

让 `dp[i][j]` 为仅使用 `S[]` 的第一个 `i` 元素和 `T[]` 的第一个 `j` 元素创建子序列的方法数，使得子序列相同，并且 `i` 元素和 `S[]` 的元素以及 `j` 元素和 `T[]` 的元素分别作为子序列的最后一个元素。

基本上，如果只考虑 `S[]` 的第一 `i` 元素和 `T[]` 的第一 `j` 元素，那么 `dp[i][j]` 就是问题的答案。如果 `S[i] != T[j]`，那么 `dp[i][j] = 0`，因为使用 `S[]` 的 `i` 元素和 `T[]` 的 `j` 元素不会结束子序列。如果 `S[i] = T[j]`，那么 `dp[i][j] = ∑_{k=1}^{i-1} ∑_{l=1}^{j-1} dp[k][l] + 1`，因为 `S[]` 的前一个指标可以是任意指标 `≤ i`。

作为基本情况，`dp[0][0] = 1`。这表示不采用任何元素的情况。这个的运行时间是 `O(N^2 * M^2)`，但是我们可以通过预计算总和来加快这个速度。

让 `sum[i][j] = ∑_{k=1}^{i} ∑_{l=1}^{j} dp[k][l]`，这是 DP 数组的 2D 前缀和。`sum[i][j] = sum[i–1][j] + sum[i][j–1] – sum[i–1][j–1] + dp[i][j]`。有了 `sum[i][j]`，现在可以在 `O(1)` 中计算每个状态 `dp[i][j]`。

由于存在 `N * M` 状态，运行时间将为 `O(N * M)`。

## 代码实现

以下是上述方法的实现：

### C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

#define mod (int)(1e9 + 7)

// Function to return the pairs of subsequences
// from S[] and subsequences from T[] such
// that both have the same content
int subsequence(int S[], int T[], int n, int m)
{

    // Create dp array
    int dp[n + 1][m + 1];

    // Base values
    for (int i = 0; i <= n; i++)
        dp[i][0] = 1;

    // Base values
    for (int j = 0; j <= m; j++)
        dp[0][j] = 1;

    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= m; ++j) {

            // Keep previous dp value
            dp[i][j] = dp[i - 1][j]
                       + dp[i][j - 1]
                       - dp[i - 1][j - 1];

            // If both elements are same
            if (S[i - 1] == T[j - 1])
                dp[i][j] += dp[i - 1][j - 1];

            dp[i][j] += mod;
            dp[i][j] %= mod;
        }
    }

    // Return the required answer
    return dp[n][m];
}

// Driver code
int main()
{
    int S[] = { 1, 1 };
    int n = sizeof(S) / sizeof(S[0]);

    int T[] = { 1, 1 };
    int m = sizeof(T) / sizeof(T[0]);

    cout << subsequence(S, T, n, m);

    return 0;
}
```

### Java

```java
// Java implementation of the approach
import java.util.*;

class GFG
{

// Function to return the pairs of subsequences
// from S[] and subsequences from T[] such
// that both have the same content
static int subsequence(int[] S, int[] T,
                       int n, int m)
{

    // Create dp array
    int [][] dp = new int[n + 1][m + 1];
    int mod = 1000000007;

    // Base values
    for (int i = 0; i <= n; i++)
        dp[i][0] = 1;

    // Base values
    for (int j = 0; j <= m; j++)
        dp[0][j] = 1;

    for (int i = 1; i <= n; ++i)
    {
        for (int j = 1; j <= m; ++j)
        {

            // Keep previous dp value
            dp[i][j] = dp[i - 1][j] +
                       dp[i][j - 1] -
                       dp[i - 1][j - 1];

            // If both elements are same
            if (S[i - 1] == T[j - 1])
                dp[i][j] += dp[i - 1][j - 1];

            dp[i][j] += mod;
            dp[i][j] %= mod;
        }
    }

    // Return the required answer
    return dp[n][m];
}

// Driver code
public static void main(String []args)
{
    int S[] = { 1, 1 };
    int n = S.length;

    int T[] = { 1, 1 };
    int m = T.length;

    System.out.println(subsequence(S, T, n, m));
}
}

// This code is contributed by Sanjit Prasad
```

### Python 3

```python
# Python3 implementation of the approach
import numpy as np

mod = int(1e9 + 7)

# Function to return the pairs of subsequences
# from S[] and subsequences from T[] such
# that both have the same content
def subsequence(S, T, n, m) :

    # Create dp array
    dp = np.zeros((n + 1, m + 1));

    # Base values
    for i in range(n + 1) :
        dp[i][0] = 1;

    # Base values
    for j in range(m + 1) :
        dp[0][j] = 1;

    for i in range(1, n + 1) :
        for j in range(1, m + 1) :

            # Keep previous dp value
            dp[i][j] = dp[i - 1][j] + dp[i][j - 1] - \
                       dp[i - 1][j - 1];

            # If both elements are same
            if (S[i - 1] == T[j - 1]) :
                dp[i][j] += dp[i - 1][j - 1];

            dp[i][j] += mod;
            dp[i][j] %= mod;

    # Return the required answer
    return dp[n][m];

# Driver code
if __name__ == "__main__" :

    S = [ 1, 1 ];
    n = len(S);

    T = [ 1, 1 ];
    m = len(T);

    print(subsequence(S, T, n, m));

# This code is contributed by kanugargng
```

### C#

```csharp
// C# implementation of the approach
using System;

class GFG
{

    // Function to return the pairs of subsequences
    // from S[] and subsequences from T[] such
    // that both have the same content
    static int subsequence(int[] S, int[] T,
                           int n, int m)
    {

        // Create dp array
        int [,] dp = new int[n + 1, m + 1];
        int mod = 1000000007;

        // Base values
        for (int i = 0; i <= n; i++)
            dp[i, 0] = 1;

        // Base values
        for (int j = 0; j <= m; j++)
            dp[0, j] = 1;

        for (int i = 1; i <= n; ++i)
        {
            for (int j = 1; j <= m; ++j)
            {

                // Keep previous dp value
                dp[i, j] = dp[i - 1, j] +
                           dp[i, j - 1] -
                           dp[i - 1, j - 1];

                // If both elements are same
                if (S[i - 1] == T[j - 1])
                    dp[i, j] += dp[i - 1, j - 1];

                dp[i, j] += mod;
                dp[i, j] %= mod;
            }
        }

        // Return the required answer
        return dp[n, m];
    }

    // Driver code
    public static void Main()
    {
        int []S = { 1, 1 };
        int n = S.Length;

        int []T = { 1, 1 };
        int m = T.Length;

        Console.WriteLine(subsequence(S, T, n, m));
    }
}

// This code is contributed by AnkitRai01
```

### JavaScript

```javascript
<script>

// JavaScript implementation of the approach

let mod = 1e9 + 7;

// Function to return the pairs of subsequences
// from S[] and subsequences from T[] such
// that both have the same content
function subsequence(S, T, n, m) {

    // Create dp array
    let dp = new Array()

    for (let i = 0; i < n + 1; i++) {
        let temp = [];
        for (let j = 0; j < m + 1; j++) {
            temp.push([])
        }
        dp.push(temp)
    }

    // Base values
    for (let i = 0; i <= n; i++)
        dp[i][0] = 1;

    // Base values
    for (let j = 0; j <= m; j++)
        dp[0][j] = 1;

    for (let i = 1; i <= n; ++i) {
        for (let j = 1; j <= m; ++j) {

            // Keep previous dp value
            dp[i][j] = dp[i - 1][j]
                + dp[i][j - 1]
                - dp[i - 1][j - 1];

            // If both elements are same
            if (S[i - 1] == T[j - 1])
                dp[i][j] += dp[i - 1][j - 1];

            dp[i][j] += mod;
            dp[i][j] %= mod;
        }
    }

    // Return the required answer
    return dp[n][m];
}

// Driver code

let S = [1, 1];
let n = S.length;

let T = [1, 1];
let m = T.length;

document.write(subsequence(S, T, n, m));

</script>
```

## 复杂度分析

**时间复杂度：** `O(N*M)`
**辅助空间：** `O(N*M)`