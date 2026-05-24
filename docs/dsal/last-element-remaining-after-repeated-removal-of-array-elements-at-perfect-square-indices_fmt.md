# 在完美平方索引处重复移除数组元素后剩余的最后一个元素

> 原文：[https://www.geeksforgeeks.org/last-element-remaining-after-repeated-removal-of-array-elements-at-perfect-square-indices/](https://www.geeksforgeeks.org/last-element-remaining-after-repeated-removal-of-array-elements-at-perfect-square-indices/)

给定一个由 `N` 个整数组成的数组 `arr[]`（基于 1 的索引），任务是在完美平方索引处重复移除数组元素后，找到最后一个剩余的元素。

## 示例

> **输入:** `arr[] = {1, 2, 3, 4, 5}`
> **输出:** `5`
> **解释:**
> 在执行完美平方索引的数组元素移除之后：
> *   移除索引 1 和 4 处的数组元素会将数组修改为 `{2, 3, 5}`。
> *   移除索引 1 处的数组元素会将数组修改为 `{3, 5}`。
> *   移除索引 1 处的数组元素会将数组修改为 `{5}`。
> 执行上述操作后，数组元素剩余为 `5`。因此，打印 `5`。
>
> **输入:** `arr[] = {2, 3, 4, 4, 2, 4, -3, 1, 1}`
> **输出:** `-3`

## 天真方法

给定的问题可以通过移除完美平方索引处的数组元素，然后将所有元素复制到新数组中来解决。继续执行此步骤，直到数组中只剩下一个元素。完成上述步骤后，打印剩余的最后一个元素。

**时间复杂度:** `O(N^2)`
**辅助空间:** `O(N)`

## 有效方法

上述方法也可以通过找到潜在的最后剩余数组元素来优化，直到该元素不存在于完美的正方形索引处。按照以下步骤解决给定的问题：

*   初始化一个变量，比如说 `ans` 为 `N`，它存储执行给定操作后的最后剩余索引。
*   迭代直到 `N` 的值大于 `1` 并执行以下步骤：
    *   找出可以丢弃的元素个数，说 `discard` 为 `sqrt(N)`。
    *   如果 `discard` 的平方是 `N`，那么 `N` 不可能是最后剩下的元素，因为它被移除了。因此将 `ans` 的值减 `1` 作为下一个潜在剩余索引。
    *   将 `N` 的值减少 `discard`。
*   完成上述步骤后，将索引 `(ans - 1)` 处的元素打印为剩余的可能元素。

下面是上述方法的实现：

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find last remaining index
// after repeated removal of perfect
// square indices
int findRemainingIndex(int N)
{
    // Initialize the ans variable as N
    int ans = N;

    // Iterate a while loop and discard
    // the possible values
    while (N > 1) {

        // Total discarded values
        int discard = int(sqrt(N));

        // Check if this forms a
        // perfect square
        if (discard * discard == N) {

            // Decrease answer by 1
            ans--;
        }

        // Subtract the value from
        // the current value of N
        N -= discard;
    }

    // Return the value remained
    return ans;
}

// Function to find last remaining element
// after repeated removal of array element
// at perfect square indices
void findRemainingElement(int arr[], int N)
{

    // Find the remaining index
    int remainingIndex = findRemainingIndex(N);

    // Print the element at that
    // index as the result
    cout << arr[remainingIndex - 1];
}

// Driver Code
signed main()
{
    int arr[] = { 2, 3, 4, 4, 2, 4, -3, 1, 1 };
    int N = sizeof(arr) / sizeof(arr[0]);
    findRemainingElement(arr, N);

    return 0;
}
```

## Java

```java
// Java implementation of the above approach
import java.util.*;
import java.lang.*;
import java.lang.Math;
class GFG {

// Function to find last remaining index
// after repeated removal of perfect
// square indices
static int findRemainingIndex(int N)
{

    // Initialize the ans variable as N
    int ans = N;

    // Iterate a while loop and discard
    // the possible values
    while (N > 1) {

        // Total discarded values
        int discard = (int)(Math.sqrt(N));

        // Check if this forms a
        // perfect square
        if (discard * discard == N) {

            // Decrease answer by 1
            ans--;
        }

        // Subtract the value from
        // the current value of N
        N -= discard;
    }

    // Return the value remained
    return ans;
}

// Function to find last remaining element
// after repeated removal of array element
// at perfect square indices
static void findRemainingElement(int arr[], int N)
{

    // Find the remaining index
    int remainingIndex = findRemainingIndex(N);

    // Print the element at that
    // index as the result
    System.out.print(arr[remainingIndex - 1]);
}

    // Driver Code
    public static void main(String[] args)
    {
        // Given input
         int arr[] = { 2, 3, 4, 4, 2, 4, -3, 1, 1 };
        int N = 9;
        findRemainingElement(arr, N);

    }
}
// This code is contributed by dwivediyash
```

## Python 3

```python
# Python 3 program for the above approach
from math import sqrt

# Function to find last remaining index
# after repeated removal of perfect
# square indices
def findRemainingIndex(N):
    # Initialize the ans variable as N
    ans = N

    # Iterate a while loop and discard
    # the possible values
    while (N > 1):
        # Total discarded values
        discard = int(sqrt(N))

        # Check if this forms a
        # perfect square
        if (discard * discard == N):
            # Decrease answer by 1
            ans -= 1

        # Subtract the value from
        # the current value of N
        N -= discard

    # Return the value remained
    return ans

# Function to find last remaining element
# after repeated removal of array element
# at perfect square indices
def findRemainingElement(arr, N):

    # Find the remaining index
    remainingIndex = findRemainingIndex(N)

    # Print the element at that
    # index as the result
    print(arr[remainingIndex - 1])

# Driver Code
if __name__ == '__main__':
    arr = [2, 3, 4, 4, 2, 4, -3, 1, 1]
    N = len(arr)
    findRemainingElement(arr, N)

    # This code is contributed by SURENDRA_GANGWAR.
```

## C#

```csharp
// C# program for the above approach
using System;

class GFG {

// Function to find last remaining index
// after repeated removal of perfect
// square indices
static int findRemainingIndex(int N)
{

    // Initialize the ans variable as N
    int ans = N;

    // Iterate a while loop and discard
    // the possible values
    while (N > 1) {

        // Total discarded values
        int discard = (int)(Math.Sqrt(N));

        // Check if this forms a
        // perfect square
        if (discard * discard == N) {

            // Decrease answer by 1
            ans--;
        }

        // Subtract the value from
        // the current value of N
        N -= discard;
    }

    // Return the value remained
    return ans;
}

// Function to find last remaining element
// after repeated removal of array element
// at perfect square indices
static void findRemainingElement(int[] arr, int N)
{

    // Find the remaining index
    int remainingIndex = findRemainingIndex(N);

    // Print the element at that
    // index as the result
    Console.Write(arr[remainingIndex - 1]);
}

    // Driver Code
    public static void Main()
    {
        // Given input
         int[] arr = { 2, 3, 4, 4, 2, 4, -3, 1, 1 };
        int N = 9;
        findRemainingElement(arr, N);
    }
}

// This code is contributed by code_hunt.
```

## java 描述语言

```javascript
<script>
        // JavaScript Program to implement
        // the above approach

        // Function to find last remaining index
        // after repeated removal of perfect
        // square indices
        function findRemainingIndex(N) {
            // Initialize the ans variable as N
            let ans = N;

            // Iterate a while loop and discard
            // the possible values
            while (N > 1) {

                // Total discarded values
                let discard = Math.floor(Math.sqrt(N));

                // Check if this forms a
                // perfect square
                if (discard * discard == N) {

                    // Decrease answer by 1
                    ans--;
                }

                // Subtract the value from
                // the current value of N
                N -= discard;
            }

            // Return the value remained
            return ans;
        }

        // Function to find last remaining element
        // after repeated removal of array element
        // at perfect square indices
        function findRemainingElement(arr, N) {

            // Find the remaining index
            let remainingIndex = findRemainingIndex(N);

            // Print the element at that
            // index as the result
            document.write(arr[remainingIndex - 1]);
        }

        // Driver Code

        let arr = [2, 3, 4, 4, 2, 4, -3, 1, 1];
        let N = arr.length;
        findRemainingElement(arr, N);

// This code is contributed by Potta Lokesh
    </script>
```

**Output:**

时间复杂度: `O(sqrt(N))`
辅助空间: `O(1)`