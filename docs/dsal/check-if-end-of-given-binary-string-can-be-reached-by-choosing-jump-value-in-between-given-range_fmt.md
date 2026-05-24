# 通过跳跃检查二进制字符串末尾可达性

> 原文: [https://www.geeksforgeeks.org/check-if-end-of-given-binary-string-can-be-reached-by-choosing-jump-value-in-between-given-range/](https://www.geeksforgeeks.org/check-if-end-of-given-binary-string-can-be-reached-by-choosing-jump-value-in-between-given-range/)

给定两个正整数 `L` 和 `R` 以及一个大小为 `N` 的[二进制字符串](https://www.geeksforgeeks.org/tag/binary-string/) `S`，任务是通过一系列的索引跳转（比如说 `i`）来检查字符串是否从索引 `0` 到达了字符串的末尾，使得 `S[i]` 为 `0`，且跳转值在范围 `[L, R]` 内。如果有可能到达，则打印 `是`。否则，打印 `否`。

**示例:**

> **输入:** `S = "011010"`, `L = 2`, `R = 3`
> **输出:** 是
> **解释:**
> 以下是在该索引处具有字符的一系列移动，如 0:
> `S[0](= 0) -> S[3](= 0) -> S[5](= 0)`，且 `S[5]` 是字符串 `S` 的结尾。
> 因此，打印是。
>
> **输入:** `S = "01101110"`, `L = 2`, `R = 3`
> **输出:** 否

**方法:** 上述问题可以借助[动态规划](https://www.geeksforgeeks.org/dynamic-programming/)解决，思路是维持一个一维数组，记作 `dp[]`，其中 `dp[i]` 将存储到达第 `i` 个位置的可能性，并相应更新各指标。以下是步骤:

*   初始化一个数组 `dp[]`，使得 `dp[i]` 存储是否可以从索引 `0` 到达任何索引 `i`。将 `dp[0]` 的值更新为 `1`，因为它是当前的起始索引。
*   初始化一个变量 `pre` 为 `0`，该变量存储当前索引可到达的索引数量。
*   [迭代范围](https://www.geeksforgeeks.org/range-based-loop-c/) `[1, N)` 并更新 `pre` 变量的值如下:
    *   如果 `i >= L`，那么将 `pre` 的值增加 `dp[i - L]`。
    *   如果 `i > R`，则 `pre` 的值递减 `dp[i - R - 1]`。
*   如果 `pre` 的值为正，那么至少有 `1` 个索引，从该索引可以到达当前索引。因此，如果 `S[i] = 0`，更新 `dp[i] = 1` 的值。
*   完成上述步骤后，如果 `dp[N - 1]` 的值为正，则打印 `是`。否则，打印 `否`。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to check if it is possible
// to reach the end of the binary string
// using the given jumps
bool canReach(string s, int L, int R)
{
    // Stores the DP states
    vector<int> dp(s.length());

    // Initial state
    dp[0] = 1;

    // Stores count of indices from which
    // it is possible to reach index i
    int pre = 0;

    // Traverse the given string
    for (int i = 1; i < s.length(); i++) {

        // Update the values of pre
        // accordingly
        if (i >= L) {
            pre += dp[i - L];
        }

        // If the jump size is out of
        // the range [L, R]
        if (i > R) {
            pre -= dp[i - R - 1];
        }

        dp[i] = (pre > 0) and (s[i] == '0');
    }

    // Return answer
    return dp[s.length() - 1];
}

// Driver Code
int main()
{
    string S = "01101110";
    int L = 2, R = 3;

    cout << (canReach(S, L, R) ? "Yes" : "No");

    return 0;
}
```

## Java

```java
// Java program for the above approach

public class GFG {

    // Function to check if it is possible
    // to reach the end of the binary string
    // using the given jumps
    static int canReach(String s, int L, int R)
    {

        // Stores the DP states
        int dp[] = new int[s.length()];

        // Initial state
        dp[0] = 1;

        // Stores count of indices from which
        // it is possible to reach index i
        int pre = 0;

        // Traverse the given string
        for (int i = 1; i < s.length(); i++) {

            // Update the values of pre
            // accordingly
            if (i >= L) {
                pre += dp[i - L];
            }

            // If the jump size is out of
            // the range [L, R]
            if (i > R) {
                pre -= dp[i - R - 1];
            }

            if (pre > 0 && s.charAt(i) == '0')
                 dp[i] = 1;
            else
                dp[i] = 0;
        }

        // Return answer
        return dp[s.length() - 1];
    }

    // Driver Code
    public static void main (String[] args)
    {
        String S = "01101110";
        int L = 2, R = 3;

        if (canReach(S, L, R) == 1)
            System.out.println("Yes");
        else
            System.out.println("No");
    }
}

// This code is contributed by AnkThon
```

## Python 3

```python
# python program for the above approach

# Function to check if it is possible
# to reach the end of the binary string
# using the given jumps

def canReach(s, L, R):

    # Stores the DP states
    dp = [0 for _ in range(len(s))]

    # Initial state
    dp[0] = 1

    # Stores count of indices from which
    # it is possible to reach index i
    pre = 0

    # Traverse the given string
    for i in range(1, len(s)):

        # Update the values of pre
        # accordingly
        if (i >= L):
            pre += dp[i - L]

        # If the jump size is out of
        # the range [L, R]
        if (i > R):
            pre -= dp[i - R - 1]

        dp[i] = (pre > 0) and (s[i] == '0')

    # Return answer
    return dp[len(s) - 1]

# Driver Code
if __name__ == "__main__":

    S = "01101110"
    L = 2
    R = 3

    if canReach(S, L, R):
        print("Yes")
    else:
        print("No")

    # This code is contributed by rakeshsahni
```

## C#

```csharp
// C#  program for the above approach
using System;
public class GFG
{

    // Function to check if it is possible
    // to reach the end of the binary string
    // using the given jumps
    static int canReach(String s, int L, int R)
    {

        // Stores the DP states
        int[] dp = new int[s.Length];

        // Initial state
        dp[0] = 1;

        // Stores count of indices from which
        // it is possible to reach index i
        int pre = 0;

        // Traverse the given string
        for (int i = 1; i < s.Length; i++)
        {

            // Update the values of pre
            // accordingly
            if (i >= L)
            {
                pre += dp[i - L];
            }

            // If the jump size is out of
            // the range [L, R]
            if (i > R)
            {
                pre -= dp[i - R - 1];
            }

            if (pre > 0 && s[i] == '0')
                dp[i] = 1;
            else
                dp[i] = 0;
        }

        // Return answer
        return dp[s.Length - 1];
    }

    // Driver Code
    public static void Main()
    {
        String S = "01101110";
        int L = 2, R = 3;

        if (canReach(S, L, R) == 1)
            Console.WriteLine("Yes");
        else
            Console.WriteLine("No");
    }
}

// This code is contributed by Saurabh
```

## JavaScript

```javascript
<script>
    // JavaScript program for the above approach

    // Function to check if it is possible
    // to reach the end of the binary string
    // using the given jumps
    const canReach = (s, L, R) => {
        // Stores the DP states
        let dp = new Array(s.length).fill(1);

        // Stores count of indices from which
        // it is possible to reach index i
        let pre = 0;

        // Traverse the given string
        for (let i = 1; i < s.length; i++) {

            // Update the values of pre
            // accordingly
            if (i >= L) {
                pre += dp[i - L];
            }

            // If the jump size is out of
            // the range [L, R]
            if (i > R) {
                pre -= dp[i - R - 1];
            }

            dp[i] = (pre > 0) && (s[i] == '0');
        }

        // Return answer
        return dp[s.length - 1];
    }

    // Driver Code
    let S = "01101110";
    let L = 2, R = 3;

    if (canReach(S, L, R)) document.write("Yes");
    else document.write("No");

// This code is contributed by rakeshsahni

</script>
```

**输出:**

```
No
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(N)`