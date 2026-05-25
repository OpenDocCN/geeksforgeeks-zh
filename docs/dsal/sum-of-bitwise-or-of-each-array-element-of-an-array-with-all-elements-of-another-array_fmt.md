# 一个数组的每个数组元素与另一个数组的所有元素的按位或之和

> 原文：[https://www.geeksforgeeks.org/sum-of-bitwise-or-of-each-array-element-of-an-array-with-all-elements-of-another-array/](https://www.geeksforgeeks.org/sum-of-bitwise-or-of-each-array-element-of-an-array-with-all-elements-of-another-array/)

给定两个大小为 `M` 的数组 `arr1[]` 和大小为 `N` 的 `arr2[]`，任务是求 `arr1[]` 的每个元素与数组 `arr2[]` 的每个元素的位 OR 之和。

**示例：**

> **输入：** `arr1[] = {1，2，3}`，`arr2[] = {1，2，3}`，`M = 3`，`N = 3`
> **输出：** `7 8 9`
> **解释：** 对于 `arr[0]`：`Sum = arr1[0] | arr2[0] + arr1[0] | arr2[1] + arr1[0] | arr2[2]`，`Sum = 1|1 + 1|2 + 1|3 = 7`
>
> **输入：** `arr1[] = {2，4，8，16}`，`arr2[] = {2，4，8，16}`，`M = 4`，`N = 4`
> **输出：** `36 42 54 78`

**天真法：** 解决这个问题最简单的方法是遍历数组 `arr1[]`，对于数组 `arr1[]` 中的每个数组元素，计算数组 `arr2[]` 中每个元素的位 OR。

**时间复杂度：** `O(N^2)`
**辅助空间：** `O(N)`

**高效途径：** 对上述途径进行优化，思路是利用位操纵解决上述问题。

*   根据逐位 OR 属性，在执行运算时，`i` 位将为置位位，只有当两个数字中的任意一个都有一个置位位在 `i` 的位置，其中 `0 ≤ i < 32`。
*   因此，对于 `arr1[]` 中的一个数，如果 `i` 位不是置位位，那么 `i` 处将贡献 `K * 2^i` 之和，其中 `K` 是 `arr2[]` 中有置位位的总数。
*   否则，如果该号码在 `i` 处有一个设置位，那么它将贡献 `N * 2^i` 之和。

按照以下步骤解决问题：

1.  初始化一个整数数组，比如 `frequency[]`，在 `i` 位置（`0 ≤ i < 32`）存储已置位的 `arr2[]` 中的数字计数。
2.  遍历数组 `arr2[]`，并以其二进制形式表示每个数组元素，并在二进制表示中具有设置位的位置将 `frequency[]` 数组中的计数增加 1。
3.  遍历数组 `arr1[]`。
    1.  初始化一个整数变量，用 `0` 表示 `bitwise_OR_sum`。
    2.  使用变量 `j` 在范围 `[0，31]` 内遍历。
    3.  如果在 `arr2[i]` 的二进制表示中设置了 `j` 位，则按 `N * 2^j` 递增 `bitwise_OR_sum`。否则，增加 `frequency[j] * 2^j`。
    4.  打印得到的和 `bitwise_OR_sum`。

下面是上述方法的实现：

## C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to compute sum of Bitwise OR
// of each element in arr1[] with all
// elements of the array arr2[]
void Bitwise_OR_sum_i(int arr1[], int arr2[],
                      int M, int N)
{

    // Declaring an array of
    // size 32 to store the
    // count of each bit
    int frequency[32] = { 0 };

    // Traverse the array arr1[]
    for (int i = 0; i < N; i++) {

        // Current bit position
        int bit_position = 0;
        int num = arr1[i];

        // While num exceeds 0
        while (num) {

            // Checks if i-th bit
            // is set or not
            if (num & 1) {

                // Increment the count at
                // bit_position by one
                frequency[bit_position] += 1;
            }

            // Increment bit_position
            bit_position += 1;

            // Right shift the num by one
            num >>= 1;
        }
    }

    // Traverse in the arr2[]
    for (int i = 0; i < M; i++) {

        int num = arr2[i];

        // Store the ith bit value
        int value_at_that_bit = 1;

        // Total required sum
        int bitwise_OR_sum = 0;

        // Traverse in the range [0, 31]
        for (int bit_position = 0;
             bit_position < 32;
             bit_position++) {

            // Check if current bit is set
            if (num & 1) {

                // Increment the Bitwise
                // sum by N*(2^i)
                bitwise_OR_sum
                    += N * value_at_that_bit;
            }
            else {
                bitwise_OR_sum
                    += frequency[bit_position]
                       * value_at_that_bit;
            }

            // Right shift num by one
            num >>= 1;

            // Left shift valee_at_that_bit by one
            value_at_that_bit <<= 1;
        }

        // Print the sum obtained for ith
        // number in arr1[]
        cout << bitwise_OR_sum << ' ';
    }

    return;
}

// Driver Code
int main()
{

    // Given arr1[]
    int arr1[] = { 1, 2, 3 };

    // Given arr2[]
    int arr2[] = { 1, 2, 3 };

    // Size of arr1[]
    int N = sizeof(arr1) / sizeof(arr1[0]);

    // Size of arr2[]
    int M = sizeof(arr2) / sizeof(arr2[0]);

    // Function Call
    Bitwise_OR_sum_i(arr1, arr2, M, N);

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.util.*;

class GFG{

// Function to compute sum of Bitwise OR
// of each element in arr1[] with all
// elements of the array arr2[]
static void Bitwise_OR_sum_i(int arr1[], int arr2[],
                             int M, int N)
{

    // Declaring an array of
    // size 32 to store the
    // count of each bit
    int frequency[] = new int[32];
    Arrays.fill(frequency, 0);

    // Traverse the array arr1[]
    for(int i = 0; i < N; i++)
    {

        // Current bit position
        int bit_position = 0;
        int num = arr1[i];

        // While num exceeds 0
        while (num != 0)
        {

            // Checks if i-th bit
            // is set or not
            if ((num & 1) != 0)
            {

                // Increment the count at
                // bit_position by one
                frequency[bit_position] += 1;
            }

            // Increment bit_position
            bit_position += 1;

            // Right shift the num by one
            num >>= 1;
        }
    }

    // Traverse in the arr2[]
    for(int i = 0; i < M; i++)
    {

        int num = arr2[i];

        // Store the ith bit value
        int value_at_that_bit = 1;

        // Total required sum
        int bitwise_OR_sum = 0;

        // Traverse in the range [0, 31]
        for(int bit_position = 0;
                bit_position < 32;
                bit_position++)
        {

            // Check if current bit is set
            if ((num & 1) != 0)
            {

                // Increment the Bitwise
                // sum by N*(2^i)
                bitwise_OR_sum += N * value_at_that_bit;
            }
            else
            {
                bitwise_OR_sum += frequency[bit_position] *
                                  value_at_that_bit;
            }

            // Right shift num by one
            num >>= 1;

            // Left shift valee_at_that_bit by one
            value_at_that_bit <<= 1;
        }

        // Print the sum obtained for ith
        // number in arr1[]
        System.out.print(bitwise_OR_sum + " ");
    }
    return;
}

// Driver code
public static void main(String[] args)
{

    // Given arr1[]
    int arr1[] = { 1, 2, 3 };

    // Given arr2[]
    int arr2[] = { 1, 2, 3 };

    // Size of arr1[]
    int N = arr1.length;

    // Size of arr2[]
    int M = arr2.length;

    // Function Call
    Bitwise_OR_sum_i(arr1, arr2, M, N);
}
}

// This code is contributed by susmitakundugoaldanga
```

## 蟒蛇 3

```python
# Python3 program for the above approach

# Function to compute sum of Bitwise OR
# of each element in arr1[] with all
# elements of the array arr2[]
def Bitwise_OR_sum_i(arr1, arr2, M, N):

    # Declaring an array of
    # size 32 to store the
    # count of each bit
    frequency = [0] * 32

    # Traverse the array arr1[]
    for i in range(N):

        # Current bit position
        bit_position = 0
        num = arr1[i]

        # While num exceeds 0
        while (num):

            # Checks if i-th bit
            # is set or not
            if (num & 1 != 0):

                # Increment the count at
                # bit_position by one
                frequency[bit_position] += 1

            # Increment bit_position
            bit_position += 1

            # Right shift the num by one
            num >>= 1

    # Traverse in the arr2[]
    for i in range(M):
        num = arr2[i]

        # Store the ith bit value
        value_at_that_bit = 1

        # Total required sum
        bitwise_OR_sum = 0

        # Traverse in the range [0, 31]
        for bit_position in range(32):

            # Check if current bit is set
            if (num & 1 != 0):

                # Increment the Bitwise
                # sum by N*(2^i)
                bitwise_OR_sum += N * value_at_that_bit

            else:
                bitwise_OR_sum += (frequency[bit_position] *
                                   value_at_that_bit)

            # Right shift num by one
            num >>= 1

            # Left shift valee_at_that_bit by one
            value_at_that_bit <<= 1

        # Print the sum obtained for ith
        # number in arr1[]
        print(bitwise_OR_sum, end = " ")

    return

# Driver Code

# Given arr1[]
arr1 = [ 1, 2, 3 ]

# Given arr2[]
arr2 = [ 1, 2, 3 ]

# Size of arr1[]
N = len(arr1)

# Size of arr2[]
M = len(arr2)

# Function Call
Bitwise_OR_sum_i(arr1, arr2, M, N)

# This code is contributed by code_hunt
```

## C\#

```csharp
// C# program for the above approach
using System;
class GFG
{

// Function to compute sum of Bitwise OR
// of each element in arr1[] with all
// elements of the array arr2[]
static void Bitwise_OR_sum_i(int[] arr1, int[] arr2,
                             int M, int N)
{

    // Declaring an array of
    // size 32 to store the
    // count of each bit
    int[] frequency = new int[32];
    for(int i = 0; i < 32; i++)
    {
        frequency[i] = 0;
    }

    // Traverse the array arr1[]
    for(int i = 0; i < N; i++)
    {

        // Current bit position
        int bit_position = 0;
        int num = arr1[i];

        // While num exceeds 0
        while (num != 0)
        {

            // Checks if i-th bit
            // is set or not
            if ((num & 1) != 0)
            {

                // Increment the count at
                // bit_position by one
                frequency[bit_position] += 1;
            }

            // Increment bit_position
            bit_position += 1;

            // Right shift the num by one
            num >>= 1;
        }
    }

    // Traverse in the arr2[]
    for(int i = 0; i < M; i++)
    {        
        int num = arr2[i];

        // Store the ith bit value
        int value_at_that_bit = 1;

        // Total required sum
        int bitwise_OR_sum = 0;

        // Traverse in the range [0, 31]
        for(int bit_position = 0;
                bit_position < 32;
                bit_position++)
        {

            // Check if current bit is set
            if ((num & 1) != 0)
            {

                // Increment the Bitwise
                // sum by N*(2^i)
                bitwise_OR_sum += N * value_at_that_bit;
            }
            else
            {
                bitwise_OR_sum += frequency[bit_position] *
                                  value_at_that_bit;
            }

            // Right shift num by one
            num >>= 1;

            // Left shift valee_at_that_bit by one
            value_at_that_bit <<= 1;
        }

        // Print the sum obtained for ith
        // number in arr1[]
        Console.Write(bitwise_OR_sum + " ");
    }
    return;
}

// Driver Code
public static void Main()
{

    // Given arr1[]
    int[] arr1 = { 1, 2, 3 };

    // Given arr2[]
    int[] arr2 = { 1, 2, 3 };

    // Size of arr1[]
    int N = arr1.Length;

    // Size of arr2[]
    int M = arr2.Length;

    // Function Call
    Bitwise_OR_sum_i(arr1, arr2, M, N);
}
}

// This code is contributed by sanjoy_62
```

## JavaScript

```javascript
<script>
// Javascript program for the above approach

// Function to compute sum of Bitwise OR
// of each element in arr1[] with all
// elements of the array arr2[]
function Bitwise_OR_sum_i(arr1, arr2, M, N) {

    // Declaring an array of
    // size 32 to store the
    // count of each bit
    let frequency = new Array(32).fill(0);

    // Traverse the array arr1[]
    for (let i = 0; i < N; i++) {

        // Current bit position
        let bit_position = 0;
        let num = arr1[i];

        // While num exceeds 0
        while (num) {

            // Checks if i-th bit
            // is set or not
            if (num & 1) {

                // Increment the count at
                // bit_position by one
                frequency[bit_position] += 1;
            }

            // Increment bit_position
            bit_position += 1;

            // Right shift the num by one
            num >>= 1;
        }
    }

    // Traverse in the arr2[]
    for (let i = 0; i < M; i++) {

        let num = arr2[i];

        // Store the ith bit value
        let value_at_that_bit = 1;

        // Total required sum
        let bitwise_OR_sum = 0;

        // Traverse in the range [0, 31]
        for (let bit_position = 0; bit_position < 32; bit_position++) {

            // Check if current bit is set
            if (num & 1) {

                // Increment the Bitwise
                // sum by N*(2^i)
                bitwise_OR_sum += N * value_at_that_bit;
            }
            else {
                bitwise_OR_sum += frequency[bit_position] * value_at_that_bit;
            }

            // Right shift num by one
            num >>= 1;

            // Left shift valee_at_that_bit by one
            value_at_that_bit <<= 1;
        }

        // Print the sum obtained for ith
        // number in arr1[]
        document.write(bitwise_OR_sum + ' ');
    }

    return;
}

// Driver Code

// Given arr1[]
let arr1 = [1, 2, 3];

// Given arr2[]
let arr2 = [1, 2, 3];

// Size of arr1[]
let N = arr1.length;

// Size of arr2[]
let M = arr2.length;

// Function Call
Bitwise_OR_sum_i(arr1, arr2, M, N);

// This code is contributed by _saurabh_jaiswal
</script>
```

**Output:**

```
7 8 9
```

**时间复杂度:** `O(N*32)`
**辅助空间:** `O(N*32)`