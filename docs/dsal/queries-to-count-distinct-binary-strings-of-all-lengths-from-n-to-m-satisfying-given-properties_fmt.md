# 对满足给定属性的从 N 到 M 的所有长度的不同二进制字符串进行计数的查询

> 原文: [https://www.geeksforgeeks.org/queries-to-count-distinct-binary-strings-of-all-lengths-from-n-to-m-satisfying-given-properties/](https://www.geeksforgeeks.org/queries-to-count-distinct-binary-strings-of-all-lengths-from-n-to-m-satisfying-given-properties/)

给定一个整数 `K` 和一个由 `{N, M}` 形式的查询组成的矩阵 `Q[][]`，每个查询的任务是计算从 `Q[i][0]` 到 `Q[i][1]` 的所有长度的可能字符串的数量，且字符串需满足以下属性：
*   字符 `0` 的出现频率等于 `K` 的倍数。
*   只有当字符 `0` 和 `1` 的频率不同时，两个字符串才被认为是不同的。

因为答案可能会很大，所以需要对 `10^9 + 7` 取模。

**示例：**

**输入**：`K = 3`，`Q[][] = {{1, 3}}`
**输出**：`4`
**解释**：
长度为 1 的所有可能字符串：`{"1"}`
长度为 2 的所有可能字符串：`{"11"}`
长度为 3 的所有可能字符串：`{"111", "000"}`
因此，总共可以生成 4 个字符串。

**输入**：`K = 3`，`Q[][] = {{1, 4}, {3, 7}}`
**输出**：
```
7
24
```

**天真方法：**
按照以下步骤解决问题：
*   初始化一个数组 `dp[]`，使得 `dp[i]` 表示长度为 `i` 的可能字符串数量。
*   初始化 `dp[0] = 1`。
*   对于每一个第 `i` 种长度，最多出现两种可能性：
    *   将字符 `"1"` 附加到长度为 `i-1` 的字符串中。
    *   将 `K` 个 `"0"` 添加到所有可能的长度为 `i-K` 的字符串中。
*   最后，对于每个查询 `Q[i]`，打印 `Q[i][0] <= j <= Q[i][1]` 的所有 `dp[j]` 之和。

**时间复杂度**：`O(N*Q)`
**辅助空间**：`O(N)`

**高效方法：**
上述方法可以使用[前缀和数组](https://www.geeksforgeeks.org/prefix-sum-array-implementation-applications-competitive-programming/)进行优化。请遵循以下步骤：
*   按照上述方法中的步骤更新 `dp[]` 数组。
*   计算 `dp[]` 数组的前缀和数组。
*   最后，对于每个查询 `Q[i]`，计算 `dp[Q[i][1]] - dp[Q[i][0] - 1]` 并打印结果。

下面是上述方法的实现：

## C++

```cpp
// C++ Program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

const int N = 1e5 + 5;
const int MOD = 1000000007;
long int dp[N];

// Function to calculate the
// count of possible strings
void countStrings(int K, vector<vector<int> > Q)
{
    // Initialize dp[0]
    dp[0] = 1;

    // dp[i] represents count of
    // strings of length i
    for (int i = 1; i < N; i++) {
        dp[i] = dp[i - 1];
        // Add dp[i-k] if i>=k
        if (i >= K)
            dp[i] = (dp[i] + dp[i - K]) % MOD;
    }

    // Update Prefix Sum Array
    for (int i = 1; i < N; i++) {
        dp[i] = (dp[i] + dp[i - 1]) % MOD;
    }

    for (int i = 0; i < Q.size(); i++) {
        long int ans = dp[Q[i][1]] - dp[Q[i][0] - 1];
        if (ans < 0)
            ans = ans + MOD;
        cout << ans << endl;
    }
}

// Driver Code
int main()
{
    int K = 3;
    vector<vector<int> > Q = { { 1, 4 }, { 3, 7 } };
    countStrings(K, Q);
    return 0;
}
```

## Java

```java
// Java program to implement
// the above approach
import java.util.*;

class GFG{
    static int N = (int)(1e5 + 5);
    static int MOD = 1000000007;
    static int []dp = new int[N];

    // Function to calculate the
    // count of possible Strings
    static void countStrings(int K, int[][] Q)
    {
        // Initialize dp[0]
        dp[0] = 1;

        // dp[i] represents count of
        // Strings of length i
        for(int i = 1; i < N; i++)
        {
            dp[i] = dp[i - 1];
            // Add dp[i-k] if i>=k
            if (i >= K)
                dp[i] = (dp[i] + dp[i - K]) % MOD;
        }

        // Update Prefix Sum Array
        for(int i = 1; i < N; i++)
        {
            dp[i] = (dp[i] + dp[i - 1]) % MOD;
        }

        for(int i = 0; i < Q.length; i++)
        {
            int ans = dp[Q[i][1]] - dp[Q[i][0] - 1];
            if (ans < 0)
                ans = ans + MOD;
            System.out.print(ans + "\n");
        }
    }

    // Driver Code
    public static void main(String[] args)
    {
        int K = 3;
        int [][]Q = { { 1, 4 }, { 3, 7 } };
        countStrings(K, Q);
    }
}

// This code is contributed by 29AjayKumar
```

## Python3

```python
# Python3 program to implement
# the above approach
N = int(1e5 + 5)
MOD = 1000000007
dp = [0] * N

# Function to calculate the
# count of possible strings
def countStrings(K, Q):
    # Initialize dp[0]
    dp[0] = 1

    # dp[i] represents count of
    # strings of length i
    for i in range(1, N):
        dp[i] = dp[i - 1]
        # Add dp[i-k] if i>=k
        if(i >= K):
            dp[i] = (dp[i] + dp[i - K]) % MOD

    # Update Prefix Sum Array
    for i in range(1, N):
        dp[i] = (dp[i] + dp[i - 1]) % MOD

    for i in range(len(Q)):
        ans = dp[Q[i][1]] - dp[Q[i][0] - 1]
        if (ans < 0):
            ans += MOD
        print(ans)

# Driver Code
K = 3
Q = [ [ 1, 4 ], [ 3, 7 ] ]
countStrings(K, Q)

# This code is contributed by Shivam Singh
```

## C#

```csharp
// C# program to implement
// the above approach
using System;
class GFG{
    static int N = (int)(1e5 + 5);
    static int MOD = 1000000007;
    static int []dp = new int[N];

    // Function to calculate the
    // count of possible Strings
    static void countStrings(int K, int[,] Q)
    {    
        // Initialize dp[0]
        dp[0] = 1;

        // dp[i] represents count of
        // Strings of length i
        for(int i = 1; i < N; i++)
        {
            dp[i] = dp[i - 1];
            // Add dp[i-k] if i>=k
            if (i >= K)
                dp[i] = (dp[i] + dp[i - K]) % MOD;
        }

        // Update Prefix Sum Array
        for(int i = 1; i < N; i++)
        {
            dp[i] = (dp[i] + dp[i - 1]) % MOD;
        }

        for(int i = 0; i < Q.GetLength(0); i++)
        {
            int ans = dp[Q[i, 1]] - dp[Q[i, 0] - 1];
            if (ans < 0)
                ans = ans + MOD;
            Console.Write(ans + "\n");
        }
    }

    // Driver Code
    public static void Main(String[] args)
    {
        int K = 3;
        int [,]Q = {{1, 4}, {3, 7}};
        countStrings(K, Q);
    }
}

// This code is contributed by 29AjayKumar
```

## JavaScript

```javascript
<script>
// Javascript program to implement
// the above approach
let N = parseInt((1e5 + 5));
let MOD = 1000000007;
let dp = Array(N).fill(0);

// Function to calculate the
// count of possible Strings
function countStrings(K, Q)
{
    // Initialize dp[0]
    dp[0] = 1;

    // dp[i] represents count of
    // Strings of length i
    for(let i = 1; i < N; i++)
    {
        dp[i] = dp[i - 1];
        // Add dp[i-k] if i>=k
        if (i >= K)
            dp[i] = (dp[i] + dp[i - K]) % MOD;
    }

    // Update Prefix Sum Array
    for(let i = 1; i < N; i++)
    {
        dp[i] = (dp[i] + dp[i - 1]) % MOD;
    }

    for(let i = 0; i < Q.length; i++)
    {
        var ans = dp[Q[i][1]] - dp[Q[i][0] - 1];
        if (ans < 0)
            ans = ans + MOD;
        document.write(ans + "<br>");
    }
}

// Driver Code
var K = 3;
let Q = [ [ 1, 4 ], [ 3, 7 ] ];
countStrings(K, Q);

// This code is contributed by gauravrajput1
</script>
```

**输出：**
```
7
24
```

**时间复杂度**：`O(N + Q)`
**辅助空间**：`O(N)`