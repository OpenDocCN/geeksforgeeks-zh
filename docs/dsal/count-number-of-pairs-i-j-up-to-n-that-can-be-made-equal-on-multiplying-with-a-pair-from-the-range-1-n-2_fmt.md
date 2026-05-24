# 计算范围 [1, N] 内满足特定乘法条件的数对数量

> 原文: [https://www.geeksforgeeks.org/count-number-of-pairs-i-j-up-to-n-that-can-be-made-equal-on-multiplying-with-a-pair-from-the-range-1-n-2/](https://www.geeksforgeeks.org/count-number-of-pairs-i-j-up-to-n-that-can-be-made-equal-on-multiplying-with-a-pair-from-the-range-1-n-2/)

给定一个正整数 `N`，任务是从范围 `[1, N]` 中找出对的数量 `(i, j)`，使得 `i` 和 `L1` 的乘积与 `j` 和 `L2` 的乘积相同，其中 `i < j`，且 `L1` 和 `L2` 均来自范围 `[1, N/2]`。

## 示例

**输入:** `N = 4`
**输出:** `2`
**解释:**
满足给定标准的可能对有:
1.  `(1, 2)`: 因为 `1 < 2`，且 `1*2 = 2*1`，其中 `L1 = 2`，`L2 = 1`。
2.  `(2, 4)`: 因为 `2 < 4`，且 `2*2 = 4*1`，其中 `L1 = 2`，`L2 = 1`。

因此，总计数为 `2`。

**输入:** `N = 6`
**输出:** `7`

## 朴素方法

给定的问题可以基于以下观察来解决:
> 设 `i * L1 = j * L2 = LCM(i, j)` (1)
> 则 `L1 = LCM(i, j) / i = j / gcd(i, j)`
> 同样，`L2 = i / gcd(i, j)`
> 现在，要满足这个条件，`L1` 和 `L2` 必须在 `[1, N/2]` 的范围内。

因此，想法是在范围 `[1, N]` 上生成所有可能的对 `(i, j)`，如果存在任何对 `(i, j)` 使得 `i/gcd(i, j)` 和 `j/gcd(i, j)` 的值都小于等于 `N/2`，则按 `1` 递增对的计数。检查所有对后，打印 `计数` 的值作为结果。

**时间复杂度:** `O(N^2 * log N)`
**辅助空间:** `O(1)`

## 高效方法

上述方法也可以通过欧拉全能性函数进行优化。任何一对 `(i, j)` 都存在以下两种情况:

*   **情况 1:** 如果配对 `(i, j)` 位于范围 `[1, N/2]` 内，那么形成的所有可能配对都将满足给定条件。因此，配对总数由 `(z * (z - 1)) / 2` 给出，其中 `z = N/2`。
*   **情况 2:** 如果所有可能的对 `(i, j)` 都在范围 `[N/2 + 1, N]` 内，且 `gcd(i, j)` 大于 `1` 则满足给定条件。

请按照以下步骤计算这类配对的总数:
*   对于所有小于或等于 `N` 的数字，使用欧拉全能性函数计算 `φ`。
*   对于一个数 `j`，可能对的总数 `(i, j)` 可以计算为 `(j - φ(j) - 1)`。
*   对于 `[N/2 + 1, N]` 范围内的每个数字，使用上述公式计算总对数。
*   完成上述步骤后，打印上述两个步骤中获得的值的总和作为结果。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to compute totient of all
// numbers smaller than or equal to N
void computeTotient(int N, int phi[])
{
    // Iterate over the range [2, N]
    for (int p = 2; p <= N; p++) {

        // If phi[p] is not computed
        // already, then p is prime
        if (phi[p] == p) {

            // Phi of a prime number
            // p is (p - 1)
            phi[p] = p - 1;

            // Update phi values of
            // all multiples of p
            for (int i = 2 * p; i <= N;
                 i += p) {

                // Add contribution of p
                // to its multiple i by
                // multiplying with (1 - 1/p)
                phi[i] = (phi[i] / p) * (p - 1);
            }
        }
    }
}

// Function to count the pairs (i, j)
// from the range [1, N], satisfying
// the given condition
void countPairs(int N)
{
    // Stores the counts of first and
    // second type of pairs respectively
    int cnt_type1 = 0, cnt_type2 = 0;

    // Count of first type of pairs
    int half_N = N / 2;
    cnt_type1 = (half_N * (half_N - 1)) / 2;

    // Stores the  phi or totient values
    int phi[N + 1];

    for (int i = 1; i <= N; i++) {
        phi[i] = i;
    }

    // Calculate the Phi values
    computeTotient(N, phi);

    // Iterate over the range
    // [N/2 + 1, N]
    for (int i = (N / 2) + 1;
         i <= N; i++)

        // Update the value of
        // cnt_type2
        cnt_type2 += (i - phi[i] - 1);

    // Print the total count
    cout << cnt_type1 + cnt_type2;
}

// Driver Code
int main()
{
    int N = 6;
    countPairs(N);

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.util.*;

class GFG{

// Function to compute totient of all
// numbers smaller than or equal to N
static void computeTotient(int N, int phi[])
{

    // Iterate over the range [2, N]
    for(int p = 2; p <= N; p++)
    {

        // If phi[p] is not computed
        // already, then p is prime
        if (phi[p] == p)
        {

            // Phi of a prime number
            // p is (p - 1)
            phi[p] = p - 1;

            // Update phi values of
            // all multiples of p
            for(int i = 2 * p; i <= N; i += p)
            {

                // Add contribution of p
                // to its multiple i by
                // multiplying with (1 - 1/p)
                phi[i] = (phi[i] / p) * (p - 1);
            }
        }
    }
}

// Function to count the pairs (i, j)
// from the range [1, N], satisfying
// the given condition
static void countPairs(int N)
{

    // Stores the counts of first and
    // second type of pairs respectively
    int cnt_type1 = 0, cnt_type2 = 0;

    // Count of first type of pairs
    int half_N = N / 2;
    cnt_type1 = (half_N * (half_N - 1)) / 2;

    // Stores the  phi or totient values
    int []phi = new int[N + 1];

    for(int i = 1; i <= N; i++)
    {
        phi[i] = i;
    }

    // Calculate the Phi values
    computeTotient(N, phi);

    // Iterate over the range
    // [N/2 + 1, N]
    for(int i = (N / 2) + 1;
            i <= N; i++)

        // Update the value of
        // cnt_type2
        cnt_type2 += (i - phi[i] - 1);

    // Print the total count
    System.out.print(cnt_type1 + cnt_type2);
}

// Driver Code
public static void main(String[] args)
{
    int N = 6;

    countPairs(N);
}
}

// This code is contributed by Amit Katiyar
```

## Python

```python
# Python3 program for the above approach

# Function to compute totient of all
# numbers smaller than or equal to N
def computeTotient(N, phi):

    # Iterate over the range [2, N]
    for p in range(2, N + 1):

        # If phi[p] is not computed
        # already then p is prime
        if phi[p] == p:

            # Phi of a prime number
            # p is (p - 1)
            phi[p] = p - 1

            # Update phi values of
            # all multiples of p
            for i in range(2 * p, N + 1, p):

                # Add contribution of p
                # to its multiple i by
                # multiplying with (1 - 1/p)
                phi[i] = (phi[i] // p) * (p - 1)

# Function to count the pairs (i, j)
# from the range [1, N], satisfying
# the given condition
def countPairs(N):

    # Stores the counts of first and
    # second type of pairs respectively
    cnt_type1 = 0
    cnt_type2 = 0

    # Count of first type of pairs
    half_N = N // 2
    cnt_type1 = (half_N * (half_N - 1)) // 2

    # Count of second type of pairs

    # Stores the  phi or totient values
    phi = [0 for i in range(N + 1)]

    for i in range(1, N + 1):
        phi[i] = i

    # Calculate the Phi values
    computeTotient(N, phi)

    # Iterate over the range
    # [N/2 + 1, N]
    for i in range((N // 2) + 1, N + 1):

        # Update the value of
        # cnt_type2
        cnt_type2 += (i - phi[i] - 1)

    # Print the total count
    print(cnt_type1 + cnt_type2)

# Driver Code
if __name__ == '__main__':

    N = 6
    countPairs(N)

    # This code is contributed by kundudinesh007.
```

# C#

```csharp
// C# program for the above approach

using System;
class GFG {
    // Function to compute totient of all
    // numbers smaller than or equal to N
    static void computeTotient(int N, int[] phi)
    {
        // Iterate over the range [2, N]
        for (int p = 2; p <= N; p++) {

            // If phi[p] is not computed
            // already, then p is prime
            if (phi[p] == p) {

                // Phi of a prime number
                // p is (p - 1)
                phi[p] = p - 1;

                // Update phi values of
                // all multiples of p
                for (int i = 2 * p; i <= N; i += p) {

                    // Add contribution of p
                    // to its multiple i by
                    // multiplying with (1 - 1/p)
                    phi[i] = (phi[i] / p) * (p - 1);
                }
            }
        }
    }

    // Function to count the pairs (i, j)
    // from the range [1, N], satisfying
    // the given condition
    static void countPairs(int N)
    {
        // Stores the counts of first and
        // second type of pairs respectively
        int cnt_type1 = 0, cnt_type2 = 0;

        // Count of first type of pairs
        int half_N = N / 2;
        cnt_type1 = (half_N * (half_N - 1)) / 2;

        // Stores the  phi or totient values
        int[] phi = new int[N + 1];

        for (int i = 1; i <= N; i++) {
            phi[i] = i;
        }

        // Calculate the Phi values
        computeTotient(N, phi);

        // Iterate over the range
        // [N/2 + 1, N]
        for (int i = (N / 2) + 1; i <= N; i++)

            // Update the value of
            // cnt_type2
            cnt_type2 += (i - phi[i] - 1);

        // Print the total count
        Console.Write(cnt_type1 + cnt_type2);
    }

    // Driver Code
    public static void Main()
    {
        int N = 6;
        countPairs(N);
    }
}

// This code is contributed by ukasp.
```

# JavaScript

```javascript
<script>

// Javascript program implementation
// of the approach

// Function to compute totient of all
// numbers smaller than or equal to N
function computeTotient(N, phi)
{

    // Iterate over the range [2, N]
    for(let p = 2; p <= N; p++)
    {

        // If phi[p] is not computed
        // already, then p is prime
        if (phi[p] == p)
        {

            // Phi of a prime number
            // p is (p - 1)
            phi[p] = p - 1;

            // Update phi values of
            // all multiples of p
            for(let i = 2 * p; i <= N; i += p)
            {

                // Add contribution of p
                // to its multiple i by
                // multiplying with (1 - 1/p)
                phi[i] = (phi[i] / p) * (p - 1);
            }
        }
    }
}

// Function to count the pairs (i, j)
// from the range [1, N], satisfying
// the given condition
function countPairs(N)
{

    // Stores the counts of first and
    // second type of pairs respectively
    let cnt_type1 = 0, cnt_type2 = 0;

    // Count of first type of pairs
    let half_N = N / 2;
    cnt_type1 = (half_N * (half_N - 1)) / 2;

    // Stores the  phi or totient values
    let phi = Array.from({length: N+1}, (_, i) => 0);

    for(let i = 1; i <= N; i++)
    {
        phi[i] = i;
    }

    // Calculate the Phi values
    computeTotient(N, phi);

    // Iterate over the range
    // [N/2 + 1, N]
    for(let i = (N / 2) + 1;
            i <= N; i++)

        // Update the value of
        // cnt_type2
        cnt_type2 += (i - phi[i] - 1);

    // Print the total count
    document.write(cnt_type1 + cnt_type2);
}

// Driver Code

    let N = 6;

    countPairs(N);

 // This code is contributed by souravghosh0416.
</script>
```

`Output:`

`时间复杂度:` `O(N * log(log(N)))`
`辅助空间:` `O(N)`