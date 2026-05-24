# 至少计算一次包含所有可能数字的 N 位数字

> 原文: [https://www.geeksforgeeks.org/count-n-digit-numbers-that-contains-every-possible-digit-atleast-once/](https://www.geeksforgeeks.org/count-n-digit-numbers-that-contains-every-possible-digit-atleast-once/)

给定一个正整数 `N`，任务是计算 `N` 位数字的个数，使得来自 `[0-9]` 的每个数字至少出现一次。

## 示例

> **输入:** `N = 10`
> **输出:** 3265920
>
> **输入:** `N = 5`
> **输出:** 0
> **说明:** 由于位数小于要求的最小位数 `[0-9]`，答案为 0。

## 天真方法

解决问题最简单的方法是生成所有可能的 `N` 位数字，并检查每个数字是否满足要求的条件。
**时间复杂度:** `O(10^N * N)`
**辅助空间:** `O(1)`

## 高效方法

优化上述方法，思路是使用[动态规划](https://www.geeksforgeeks.org/dynamic-programming/)，因为它有[重叠子问题](https://www.geeksforgeeks.org/overlapping-subproblems-property-in-dynamic-programming-dp-1/)和[最优子结构](https://www.geeksforgeeks.org/optimal-substructure-property-in-dynamic-programming-dp-2/)。子问题可以使用记忆存储在 `dp[][]` 表中，其中 `dp[digit][mask]` 存储从 `digit` 位置到结束的答案，当包含的数字使用 `mask` 表示时。

按照以下步骤解决此问题:

*   定义一个递归函数，比如 `countOfNumbers(digit, mask)`，执行以下步骤:
    *   **基本情况:** 如果 `digit` 的值等于 `N+1`，则检查 `mask` 的值是否等于 `(1<<10)-1`。如果发现为真，则返回 `1` 作为有效的 `N` 位数字形成。
    *   如果状态 `dp[digit][mask]` 的结果已经计算出来，则返回该状态 `dp[digit][mask]`。
    *   如果当前位置为 `1`，则可以放置 `[1-9]` 中的任意一个数字。如果 `N` 等于 `1`，那么 `0` 也可以放置。
    *   对于任何其他位置，可以放置从 `[0-9]` 开始的任何数字。
    *   如果包含特定数字 `i`，则将 `mask` 更新为 `mask = mask | (1 << i)`。
    *   在进行有效放置后，递归调用 `countOfNumbers` 函数到索引 `digit+1`。
    *   返回所有可能的有效数字位置的总和作为答案。

## 下面是上述方法的实现

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Stores the dp-states
long long dp[100][1 << 10];

// Function to calculate the count of
// N-digit numbers that contains all
// digits from [0-9] atleast once
long long countOfNumbers(int digit,
                         int mask, int N)
{
    // If all digits are traversed
    if (digit == N + 1) {

        // Check if all digits are
        // included in the mask
        if (mask == (1 << 10) - 1)
            return 1;
        return 0;
    }

    long long& val = dp[digit][mask];

    // If the state has
    // already been computed
    if (val != -1)
        return val;

    val = 0;

    // If the current digit is 1, any
    // digit from [1-9] can be placed.
    // If N==1, 0 can also be placed
    if (digit == 1) {
        for (int i = (N == 1 ? 0 : 1); i <= 9; ++i) {

            val += countOfNumbers(digit + 1,
                                  mask | (1 << i), N);
        }
    }

    // For other positions, any digit
    // from [0-9] can be placed
    else {
        for (int i = 0; i <= 9; ++i) {

            val += countOfNumbers(digit + 1,
                                  mask | (1 << i), N);
        }
    }

    // Return the answer
    return val;
}

// Driver Code
int main()
{
    // Initializing dp array with -1.
    memset(dp, -1, sizeof dp);

    // Given Input
    int N = 10;

    // Function Call
    cout << countOfNumbers(1, 0, N);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.util.*;

class GFG{

    // Stores the dp-states
    static int dp[][] = new int[100][1 << 10];

    // Function to calculate the count of
    // N-digit numbers that contains all
    // digits from [0-9] atleast once
    static long countOfNumbers(int digit,
                               int mask, int N)
    {
        // If all digits are traversed
        if (digit == N + 1) {

            // Check if all digits are
            // included in the mask
            if (mask == (1 << 10) - 1)
                return 1;

            return 0;
        }

        long val = dp[digit][mask];

        // If the state has
        // already been computed
        if (val != -1)
            return val;

        val = 0;

        // If the current digit is 1, any
        // digit from [1-9] can be placed.
        // If N==1, 0 can also be placed
        if (digit == 1) {
            for (int i = (N == 1 ? 0 : 1); i <= 9; ++i) {

                val += countOfNumbers(digit + 1,
                                      mask | (1 << i), N);
            }
        }

        // For other positions, any digit
        // from [0-9] can be placed
        else {
            for (int i = 0; i <= 9; ++i) {

                val += countOfNumbers(digit + 1,
                                      mask | (1 << i), N);
            }
        }

        // Return the answer
        return val;
    }

    // Driver Code
    public static void main(String[] args)
    {

        // Initializing dp array with -1.
        for(int i =0;i<dp.length;i++)
            Arrays.fill(dp[i], -1);

        // Given Input
        int N = 10;

        // Function Call
        System.out.print(countOfNumbers(1, 0, N));

    }
}

// This code is contributed by Rajput-Ji
```

### JavaScript

```javascript
<script>

// JavaScript program for the above approach

// Stores the dp-states
let dp = new Array(100);
for (let i = 0; i < 100; i++) {
    dp[i] = new Array(1 << 10).fill(-1);
}

// Function to calculate the count of
// N-digit numbers that contains all
// digits from [0-9] atleast once
function countOfNumbers(digit, mask, N)
{
    // If all digits are traversed
    if (digit == N + 1) {

        // Check if all digits are
        // included in the mask
        if (mask == (1 << 10) - 1)
            return 1;
        return 0;
    }

    let val = dp[digit][mask];

    // If the state has
    // already been computed
    if (val != -1)
        return val;

    val = 0;

    // If the current digit is 1, any
    // digit from [1-9] can be placed.
    // If N==1, 0 can also be placed
    if (digit == 1) {
        for (let i = (N == 1 ? 0 : 1); i <= 9; ++i) {

            val += countOfNumbers(digit + 1,
                                  mask | (1 << i), N);
        }
    }

    // For other positions, any digit
    // from [0-9] can be placed
    else {
        for (let i = 0; i <= 9; ++i) {

            val += countOfNumbers(digit + 1,
                                  mask | (1 << i), N);
        }
    }

    // Return the answer
    return val;
}

// Driver Code

// Given Input
let N = 10;

// Function Call
document.write(countOfNumbers(1, 0, N));

</script>
```

**Output:**

```
3265920
```

**时间复杂度:** `O(N * 2^10)`
**辅助空间:** `O(N * 2^10)`