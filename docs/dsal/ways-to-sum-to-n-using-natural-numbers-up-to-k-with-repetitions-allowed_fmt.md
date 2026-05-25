# 允许重复使用最多 K 个自然数求和为 N 的方法

> 原文: [https://www.geeksforgeeks.org/ways-to-sum-to-n-using-natural-numbers-up-to-k-with-repetitions-allowed/](https://www.geeksforgeeks.org/ways-to-sum-to-n-using-natural-numbers-up-to-k-with-repetitions-allowed/)

给定两个整数 `N` 和 `K`，任务是在 `[1, K]` 范围内找到将 `N` 表示为正整数之和的方式总数，其中每个整数可以选择多次。

## 示例

**输入:** `N = 8`，`K = 2`
**输出:** `5`
**解释:** 将 `N` 表示为小于或等于 `K` 的正整数之和的所有可能方式是:
1.  `{1, 1, 1, 1, 1, 1, 1, 1}`，总和是 `8`。
2.  `{2, 1, 1, 1, 1, 1, 1}`，总和是 `8`。
3.  `{2, 2, 1, 1, 1, 1}`，总和是 `8`。
4.  `{2, 2, 2, 1, 1}`，总和是 `8`。
5.  `{2, 2, 2, 2}`，总和是 `8`。

因此，途径总数为 `5`。

**输入:** `N = 2`，`K = 2`
**输出:** `2`

## 天真方法

解决给定问题最简单的方法是在 `[1, K]` 范围内生成选择整数的所有可能组合，并计算那些和为 `N` 的组合。

**时间复杂度:** `O(K^N)`
**辅助空间:** `O(1)`

## 有效方法

上述方法有[重叠子问题](https://www.geeksforgeeks.org/overlapping-subproblems-property-in-dynamic-programming-dp-1/)和[最优子结构](https://www.geeksforgeeks.org/optimal-substructure-property-in-dynamic-programming-dp-2/)。因此，为了优化，需要基于以下观察执行[动态规划](https://www.geeksforgeeks.org/dynamic-programming/):

*   考虑到 `dp[i]` 将表示 `i` 的方式总数存储为位于范围 `[1, K]` 内的整数之和，那么状态的转变可以定义为:
    *   对于范围 `[1, K]` 中的 `i` 和范围 `[1, N]` 中的每个 `j`
    *   `dp[j]` 的值等于 `(dp[j] + dp[j - i])`，对于所有 `j >= i`。

按照以下步骤解决问题:

1.  初始化一个[数组](https://www.geeksforgeeks.org/array-data-structure/)，比如 `dp[]`，所有元素为 `0`，存储所有递归状态。
2.  将 `dp[0]` 初始化为 `1`。
3.  现在，[使用变量 `i` 迭代范围](https://www.geeksforgeeks.org/range-based-loop-c/) `[1, K]`，并执行以下步骤:
    *   迭代范围 `[1, N]`，使用变量 `j`，如果 `j >= i`，将 `dp[j]` 的值更新为 `dp[j] + dp[j - i]`。
4.  完成上述步骤后，打印 `dp[N]` 的值作为结果。

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the total number of
// ways to represent N as the sum of
// integers over the range [1, K]
int NumberOfways(int N, int K)
{

    // Initialize a list
    vector<int> dp(N + 1, 0);

    // Update dp[0] to 1
    dp[0] = 1;

    // Iterate over the range [1, K + 1]
    for (int row = 1; row < K + 1; row++)
    {

        // Iterate over the range [1, N + 1]
        for (int col = 1; col < N + 1; col++)
        {

            // If col is greater
            // than or equal to row
            if (col >= row)

                // Update current
                // dp[col] state
                dp[col] = dp[col] + dp[col - row];
          }
    }

    // Return the total number of ways
    return(dp[N]);
}

// Driver Code
int main()
{
  int N = 8;
  int K = 2;

  cout << (NumberOfways(N, K));
}

// This code is contributed by mohit kumar 29.
```

### Java

```java
// Java program for the above approach
import java.util.*;

class GFG{

// Function to find the total number of
// ways to represent N as the sum of
// integers over the range [1, K]
static int NumberOfways(int N, int K)
{

    // Initialize a list
    int[] dp = new int[N + 1];

    // Update dp[0] to 1
    dp[0] = 1;

    // Iterate over the range [1, K + 1]
    for(int row = 1; row < K + 1; row++)
    {

        // Iterate over the range [1, N + 1]
        for(int col = 1; col < N + 1; col++)
        {

            // If col is greater
            // than or equal to row
            if (col >= row)

                // Update current
                // dp[col] state
                dp[col] = dp[col] + dp[col - row];
          }
    }

    // Return the total number of ways
    return(dp[N]);
}

// Driver code
public static void main(String[] args)
{

    // Given inputs
    int N = 8;
    int K = 2;

    System.out.println(NumberOfways(N, K));
}
}

// This code is contributed by offbeat
```

### Python

```python
# Python program for the above approach

# Function to find the total number of
# ways to represent N as the sum of
# integers over the range [1, K]
def NumberOfways(N, K):

    # Initialize a list
    dp = [0] * (N + 1)

    # Update dp[0] to 1
    dp[0] = 1

    # Iterate over the range [1, K + 1]
    for row in range(1, K + 1):

        # Iterate over the range [1, N + 1]
        for col in range(1, N + 1):

            # If col is greater
            # than or equal to row
            if (col >= row):

                # Update current
                # dp[col] state
                dp[col] = dp[col] + dp[col - row]

    # Return the total number of ways
    return(dp[N])

# Driver Code

N = 8
K = 2

print(NumberOfways(N, K))
```

### C\#

```csharp
// C# program for the above approach
using System;
class GFG
{

    // Function to find the total number of
    // ways to represent N as the sum of
    // integers over the range [1, K]
    static int NumberOfways(int N, int K)
    {

        // Initialize a list
        int[] dp = new int[(N + 1)];

        // Update dp[0] to 1
        dp[0] = 1;

        // Iterate over the range [1, K + 1]
        for (int row = 1; row < K + 1; row++) {

            // Iterate over the range [1, N + 1]
            for (int col = 1; col < N + 1; col++) {

                // If col is greater
                // than or equal to row
                if (col >= row)

                    // Update current
                    // dp[col] state
                    dp[col] = dp[col] + dp[col - row];
            }
        }

        // Return the total number of ways
        return (dp[N]);
    }

    // Driver Code
    public static void Main()
    {
        int N = 8;
        int K = 2;

        Console.WriteLine(NumberOfways(N, K));
    }
}

// This code is contributed by ukasp.
```

### JavaScript

```javascript
<script>
// Javascript implementation for the above approach

// Function to find the total number of
// ways to represent N as the sum of
// integers over the range [1, K]
function NumberOfways(N, K)
{

    // Initialize a list
    let dp = Array.from({length: N +1}, (_, i) => 0);

    // Update dp[0] to 1
    dp[0] = 1;

    // Iterate over the range [1, K + 1]
    for(let row = 1; row < K + 1; row++)
    {

        // Iterate over the range [1, N + 1]
        for(let col = 1; col < N + 1; col++)
        {

            // If col is greater
            // than or equal to row
            if (col >= row)

                // Update current
                // dp[col] state
                dp[col] = dp[col] + dp[col - row];
          }
    }

    // Return the total number of ways
    return(dp[N]);
}

    // Driver Code

    // Given inputs
    let N = 8;
    let K = 2;

    document.write(NumberOfways(N, K));

</script>
```

**输出:**

```
5
```

**时间复杂度:** `O(N * K)`
**辅助空间:** `O(N)`