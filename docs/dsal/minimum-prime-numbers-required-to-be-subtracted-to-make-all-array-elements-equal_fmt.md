# 使所有数组元素相等所需减去的最小素数

> 原文：[https://www.geeksforgeeks.org/minimum-prime-numbers-required-to-be-subtracted-to-make-all-array-elements-equal/](https://www.geeksforgeeks.org/minimum-prime-numbers-required-to-be-subtracted-to-make-all-array-elements-equal/)

给定一个由 `N` 个正整数组成的数组 `arr[]`，任务是找出需要从数组元素中减去的素数的最小个数，使所有数组元素相等。

## 示例

**输入：** `arr[] = {7, 10, 4, 5}`
**输出：** 5
**解释：** 在减去素数后，所有数组元素相等：
1.  从 `arr[0]` 中减去 5 会将 `arr[]` 修改为 `{2, 10, 4, 5}`。
2.  从 `arr[1]` 中减去 5 会将 `arr[]` 修改为 `{2, 5, 4, 5}`。
3.  从 `arr[1]` 中减去 3 会将 `arr[]` 修改为 `{2, 2, 4, 5}`。
4.  从 `arr[2]` 中减去 2 会将 `arr[]` 修改为 `{2, 2, 2, 5}`。
5.  从 `arr[3]` 中减去 3 会将 `arr[]` 修改为 `{2, 2, 2, 2}`。

因此，所需的操作总数为 5。

**输入：** `arr[] = {10, 17, 37, 43, 50}`
**输出：** 8

## 方法

给定的问题可以使用以下观察值来解决：
*   每一个大于 `2` 的偶数都是两个素数的和。
*   每一个大于 `1` 的奇数，可以表示为**至多 3 个**素数的和。以下是相同的可能情况：
    *   **情况 1：** 如果 `N` 是质数。
    *   **情况 2：** 如果 `(N–2)` 是质数。因此，需要 2 个数字，即 `2` 和 `N–2`。
    *   **情况 3：** 如果 `(N–3)` 是偶数，那么使用哥德巴赫猜想。`(N–3)` 可以表示为两个素数之和。
*   因此，想法是将每个数组元素减少到数组的最小值（比如说 `M`）`arr[]`。如果数组中存在一个值为 `(M + 1)` 的元素，那么将每个元素减少到值 `(M–2)`。

按照以下步骤解决此问题：
*   初始化一个数组，比如说 `prime[]`，大小为 `10^5`，在每个 `i` 索引处存储 `i` 是否为素数，使用厄拉多塞的筛子。
*   找到数组中存在的最小元素，说 `M`。
*   如果数组 `arr[]` 中存在值为 `(M + 1)` 的元素，则更新 `M` 为 `(M–2)`。
*   初始化一个变量，比如 `count`，来存储使所有数组元素相等所需的操作次数。
*   遍历给定数组 `arr[]`，并执行以下步骤：
    *   找出 `arr[i]` 和 `M` 的区别，说 `D`。
    *   根据以下 `D` 的值更新 `count` 的值：
        *   如果 `D` 的值是一个质数，那么将 `count` 增加 `1`。
        *   如果 `D` 的值为偶数，则按 `2` 递增 `count`。
        *   如果 `D` 的值是一个奇数，如果 `(D–2)` 是一个素数，那么将 `count` 增加 `2`。否则，将 `count` 增加 `3`。
*   完成上述步骤后，打印 `count` 的值作为结果。

下面是上述方法的实现：

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
#define limit 100000
using namespace std;

// Stores the sieve of prime numbers
bool prime[limit + 1];

// Function that performs the Sieve of
// Eratosthenes
void sieve()
{
    // Initialize all numbers as prime
    memset(prime, true, sizeof(prime));

    // Iterate over the range [2, 1000]
    for (int p = 2; p * p <= limit; p++) {

        // If the current element
        // is a prime number
        if (prime[p] == true) {

            // Mark all its multiples as false
            for (int i = p * p; i <= limit; i += p)
                prime[i] = false;
        }
    }
}

// Function to find the minimum number of
// subtraction of primes numbers required
// to make all array elements the same
int findOperations(int arr[], int n)
{
    // Perform sieve of eratosthenes
    sieve();

    int minm = INT_MAX;

    // Find the minimum value
    for (int i = 0; i < n; i++) {
        minm = min(minm, arr[i]);
    }

    // Stores the value to each array
    // element should be reduced
    int val = minm;

    for (int i = 0; i < n; i++) {

        // If an element exists with
        // value (M + 1)
        if (arr[i] == minm + 1) {
            val = minm - 2;
            break;
        }
    }

    // Stores the minimum count of
    // subtraction of prime numbers
    int cnt = 0;

    // Traverse the array
    for (int i = 0; i < n; i++) {

        int D = arr[i] - val;

        // If D is equal to 0
        if (D == 0) {
            continue;
        }

        // If D is a prime number
        else if (prime[D] == true) {

            // Increase count by 1
            cnt += 1;
        }

        // If D is an even number
        else if (D % 2 == 0) {

            // Increase count by 2
            cnt += 2;
        }
        else {

            // If D - 2 is prime
            if (prime[D - 2] == true) {

                // Increase count by 2
                cnt += 2;
            }

            // Otherwise, increase
            // count by 3
            else {
                cnt += 3;
            }
        }
    }

    return cnt;
}

// Driver Code
int main()
{
    int arr[] = { 7, 10, 4, 5 };
    int N = 4;
    cout << findOperations(arr, N);

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.io.*;
import java.lang.*;
import java.util.*;

class GFG{

static int limit = 100000;

// Stores the sieve of prime numbers
static boolean prime[];

// Function that performs the Sieve of
// Eratosthenes
static void sieve()
{
    prime = new boolean[limit + 1];

    // Initialize all numbers as prime
    Arrays.fill(prime, true);

    // Iterate over the range [2, 1000]
    for(int p = 2; p * p <= limit; p++)
    {

        // If the current element
        // is a prime number
        if (prime[p] == true)
        {

            // Mark all its multiples as false
            for(int i = p * p; i <= limit; i += p)
                prime[i] = false;
        }
    }
}

// Function to find the minimum number of
// subtraction of primes numbers required
// to make all array elements the same
static int findOperations(int arr[], int n)
{

    // Perform sieve of eratosthenes
    sieve();

    int minm = Integer.MAX_VALUE;

    // Find the minimum value
    for(int i = 0; i < n; i++)
    {
        minm = Math.min(minm, arr[i]);
    }

    // Stores the value to each array
    // element should be reduced
    int val = minm;

    for(int i = 0; i < n; i++)
    {

        // If an element exists with
        // value (M + 1)
        if (arr[i] == minm + 1)
        {
            val = minm - 2;
            break;
        }
    }

    // Stores the minimum count of
    // subtraction of prime numbers
    int cnt = 0;

    // Traverse the array
    for(int i = 0; i < n; i++)
    {
        int D = arr[i] - val;

        // If D is equal to 0
        if (D == 0)
        {
            continue;
        }

        // If D is a prime number
        else if (prime[D] == true)
        {

            // Increase count by 1
            cnt += 1;
        }

        // If D is an even number
        else if (D % 2 == 0)
        {

            // Increase count by 2
            cnt += 2;
        }
        else
        {

            // If D - 2 is prime
            if (prime[D - 2] == true)
            {

                // Increase count by 2
                cnt += 2;
            }

            // Otherwise, increase
            // count by 3
            else
            {
                cnt += 3;
            }
        }
    }
    return cnt;
}

// Driver Code
public static void main(String[] args)
{
    int arr[] = { 7, 10, 4, 5 };
    int N = 4;

    System.out.println(findOperations(arr, N));
}
}

// This code is contributed by Kingash
```

## 蟒蛇 3

```python
# Python3 program for the above approach
import sys

limit = 100000

# Stores the sieve of prime numbers
prime = [True] * (limit + 1)

# Function that performs the Sieve of
# Eratosthenes
def sieve():

    # Iterate over the range [2, 1000]
    p = 2
    while(p * p <= limit):

        # If the current element
        # is a prime number
        if (prime[p] == True):

            # Mark all its multiples as false
            for i in range(p * p, limit, p):
                prime[i] = False

        p += 1

# Function to find the minimum number of
# subtraction of primes numbers required
# to make all array elements the same
def findOperations(arr, n):

    # Perform sieve of eratosthenes
    sieve()

    minm = sys.maxsize

    # Find the minimum value
    for i in range(n):
        minm = min(minm, arr[i])

    # Stores the value to each array
    # element should be reduced
    val = minm

    for i in range(n):

        # If an element exists with
        # value (M + 1)
        if (arr[i] == minm + 1):
            val = minm - 2
            break

    # Stores the minimum count of
    # subtraction of prime numbers
    cnt = 0

    # Traverse the array
    for i in range(n):
        D = arr[i] - val

        # If D is equal to 0
        if (D == 0):
            continue

        # If D is a prime number
        elif (prime[D] == True):

            # Increase count by 1
            cnt += 1

        # If D is an even number
        elif (D % 2 == 0):

            # Increase count by 2
            cnt += 2

        else:

            # If D - 2 is prime
            if (prime[D - 2] == True):

                # Increase count by 2
                cnt += 2

            # Otherwise, increase
            # count by 3
            else:
                cnt += 3

    return cnt

# Driver Code
arr = [ 7, 10, 4, 5 ]
N = 4

print(findOperations(arr, N))

# This code is contributed by splevel62
```

## C#

```csharp
// C# program for the above approach
using System;

class GFG{

static int limit = 100000;

// Stores the sieve of prime numbers
static bool[] prime;

// Function that performs the Sieve of
// Eratosthenes
static void sieve()
{
    prime = new bool[limit + 1];

    // Initialize all numbers as prime
    Array.Fill(prime, true);

    // Iterate over the range [2, 1000]
    for(int p = 2; p * p <= limit; p++)
    {

        // If the current element
        // is a prime number
        if (prime[p] == true)
        {

            // Mark all its multiples as false
            for(int i = p * p; i <= limit; i += p)
                prime[i] = false;
        }
    }
}

// Function to find the minimum number of
// subtraction of primes numbers required
// to make all array elements the same
static int findOperations(int[] arr, int n)
{

    // Perform sieve of eratosthenes
    sieve();

    int minm = Int32.MaxValue;

    // Find the minimum value
    for(int i = 0; i < n; i++)
    {
        minm = Math.Min(minm, arr[i]);
    }

    // Stores the value to each array
    // element should be reduced
    int val = minm;

    for(int i = 0; i < n; i++)
    {

        // If an element exists with
        // value (M + 1)
        if (arr[i] == minm + 1)
        {
            val = minm - 2;
            break;
        }
    }

    // Stores the minimum count of
    // subtraction of prime numbers
    int cnt = 0;

    // Traverse the array
    for(int i = 0; i < n; i++)
    {
        int D = arr[i] - val;

        // If D is equal to 0
        if (D == 0)
        {
            continue;
        }

        // If D is a prime number
        else if (prime[D] == true)
        {

            // Increase count by 1
            cnt += 1;
        }

        // If D is an even number
        else if (D % 2 == 0)
        {

            // Increase count by 2
            cnt += 2;
        }
        else
        {

            // If D - 2 is prime
            if (prime[D - 2] == true)
            {

                // Increase count by 2
                cnt += 2;
            }

            // Otherwise, increase
            // count by 3
            else
            {
                cnt += 3;
            }
        }
    }
    return cnt;
}

// Driver Code
public static void Main(string[] args)
{
    int[] arr = { 7, 10, 4, 5 };
    int N = 4;

    Console.WriteLine(findOperations(arr, N));
}
}

// This code is contributed by ukasp
```

## java 描述语言

```javascript
<script>

// Javascript program for the above approach

var limit = 100000;

// Stores the sieve of prime numbers
var prime = Array(limit + 1).fill(true);

// Function that performs the Sieve of
// Eratosthenes
function sieve()
{

    // Iterate over the range [2, 1000]
    for (p = 2; p * p <= limit; p++) {

        // If the current element
        // is a prime number
        if (prime[p] == true) {

            // Mark all its multiples as false
            for (i = p * p; i <= limit; i += p)
                prime[i] = false;
        }
    }
}

// Function to find the minimum number of
// subtraction of primes numbers required
// to make all array elements the same
function findOperations(arr, n)
{
    // Perform sieve of eratosthenes
    sieve();

    var minm = Number.MAX_VALUE;

    // Find the minimum value
    for (i = 0; i < n; i++) {
        minm = Math.min(minm, arr[i]);
    }

    // Stores the value to each array
    // element should be reduced
    var val = minm;

    for (i = 0; i < n; i++) {

        // If an element exists with
        // value (M + 1)
        if (arr[i] == minm + 1) {
            val = minm - 2;
            break;
        }
    }

    // Stores the minimum count of
    // subtraction of prime numbers
    var cnt = 0;

    // Traverse the array
    for (i = 0; i < n; i++) {

        var D = arr[i] - val;

        // If D is equal to 0
        if (D == 0) {
            continue;
        }

        // If D is a prime number
        else if (prime[D] == true) {

            // Increase count by 1
            cnt += 1;
        }

        // If D is an even number
        else if (D % 2 == 0) {

            // Increase count by 2
            cnt += 2;
        }
        else {

            // If D - 2 is prime
            if (prime[D - 2] == true) {

                // Increase count by 2
                cnt += 2;
            }

            // Otherwise, increase
            // count by 3
            else {
                cnt += 3;
            }
        }
    }

    return cnt;
}

// Driver Code

    var arr = [7, 10, 4, 5];
    var N = 4;
    document.write(findOperations(arr, N));

</script>
```

### Output:

### 时间复杂度与辅助空间

时间复杂度: `O(N + M * log(log(M)))`，其中 `M` 大小为 `limit`。
辅助空间: `O(M)`