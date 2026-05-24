# 找到大小为 2*N 的非递减数组 brr[]，使得每个 arr[i] 等于 brr[i] 和 brr[2 * N–i+1] 之和

> 原文: [https://www.geeksforgeeks.org/find-non-decreasing-array-brr-of-size-2n-such-that-each-arri-equals-sum-of-brri-and-brr2n-i-1/](https://www.geeksforgeeks.org/find-non-decreasing-array-brr-of-size-2n-such-that-each-arri-equals-sum-of-brri-and-brr2n-i-1/)

## 问题描述

给定一个大小为 `N` 的数组 `arr[]`，任务是找到另一个大小为 `2*N` 的数组 `brr[]`，使其不递减，并且对于从 `1` 到 `N` 的每个 `i`，满足 `arr[i] = brr[i] + brr[2*N - i + 1]`。

## 示例

**输入:** `n = 2`，`arr[] = { 5，6 }`
**输出:** `0 1 5 5`
**说明:** 对于 `i = 1`，`arr[1] = 5`，`brr[1] + brr[2*2 - 1 + 1] = 5`，所以两者相等。对于 `i = 2`，`arr[2] = 6`，`brr[2] + brr[2*2 - 2 + 1] = 6`，所以两者相等。

**输入:** `n = 3`，`arr[] = { 2，1，2 }`
**输出:** `0 0 1 1 1 2`

## 方法

数组 `brr[]` 的元素将恢复成对 `(brr[1], brr[2*n])`、`(brr[2], brr[2*n-1])` 等。因此，满足上述条件的这些值可以有一定的限制：`brr[i] + brr[2*N - i - 1] == arr[i]`。

让 `l` 成为最小可能值，让 `r` 成为答案中最大可能值。最初，`l = 0`，`r = 10^18`。它们更新为 `l = brr[i]`，`r = brr[2*n - i - 1]`。

按照以下步骤解决问题：

1.  将变量 `l` 初始化为 `0`，将 `r` 初始化为 `INF64`。
2.  将 `N` 的值乘以 `2` 来计算第二个数组的大小。
3.  定义一个函数 `brute(ind, l, r)`，其中 `ind` 是要填充值的数组的索引，`l` 和 `r` 是值的范围。递归调用此函数计算第二个数组 `brr[]` 中每对的值。
4.  在函数 `brute(ind, l, r)` 中：
    *   定义基本情况，即当 `ind` 的值等于第一个数组 `arr[]` 的大小时。
    *   如果是，则打印第二个数组的元素 `brr[]` 并退出函数。
    *   否则，在范围 `[l, arr[ind]/2]` 中迭代，并执行以下步骤：
        *   如果 `arr[ind] - i` 的值小于等于 `r`，则将 `brr[ind]` 的值设置为 `i`，`brr[n - ind - 1]` 设置为 `arr[ind] - i`。
        *   将 `l` 的值设置为 `i`，并将 `r` 设置为 `arr[ind] - i`，作为 `l` 和 `r` 的更新值。
        *   为下一个索引递归调用相同的函数 `brute(ind + 1, l, r)`。

下面是上述方法的实现。

### C++

```cpp
// C++ program for the above approach.
#include <bits/stdc++.h>
using namespace std;

const long long INF64 = 1000000000000000000ll;
const int N = 200 * 1000 + 13;

int n;
long long arr[N], brr[N];

// Function to find the possible
// output array
void brute(int ind, long long l, long long r)
{
    // Base case for the recursion
    if (ind == n / 2) {
        // If ind becomes half of the size
        // then print the array.
        for (int i = 0; i < int(n); i++)
            printf("%lld ", brr[i]);
        puts("");
        // Exit the function.
        exit(0);
    }

    // Iterate in the range.
    for (long long i = l; i <= arr[ind] / 2; ++i)
        if (arr[ind] - i <= r) {
            // Put the values in the respective
            // indices.
            brr[ind] = i;
            brr[n - ind - 1] = arr[ind] - i;

            // Call the function to find values for
            // other indices.
            brute(ind + 1, i, arr[ind] - i);
        }
}

// Driver Code
int main()
{
    n = 2;
    n *= 2;

    arr[0] = 5;
    arr[1] = 6;

    brute(0, 0, INF64);
    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.io.*;

class GFG{

static int INF64 = (int)1e10;
static int N = 200 * 1000 + 13;

static int n;
static int arr[] = new int[N];
static int brr[] = new int[N];

// Function to find the possible
// output array
static void brute(int ind, int l, int r)
{

    // Base case for the recursion
    if (ind == n / 2)
    {

        // If ind becomes half of the size
        // then print the array.
        for(int i = 0; i < (int)n; i++)
            System.out.print(brr[i] + " ");

        // Exit the function.
        System.exit(0);
    }

    // Iterate in the range.
    for(int i = l; i <= arr[ind] / 2; ++i)
        if (arr[ind] - i <= r)
        {

            // Put the values in the respective
            // indices.
            brr[ind] = i;
            brr[n - ind - 1] = arr[ind] - i;

            // Call the function to find values for
            // other indices.
            brute(ind + 1, i, arr[ind] - i);
        }
}

// Driver code
public static void main(String[] args)
{
    n = 2;
    n *= 2;

    arr[0] = 5;
    arr[1] = 6;

    brute(0, 0, INF64);
}
}
```

### Python 3

```python
# Python 3 program for the above approach.

N = 200 * 1000 + 13

n = 0
arr = [0 for i in range(N)]
brr = [0 for i in range(N)]

import sys

# Function to find the possible
# output array
def brute(ind, l, r):

    # Base case for the recursion
    if (ind == n / 2):

        # If ind becomes half of the size
        # then print the array.
        for i in range(n):
            print(brr[i],end = " ")

        # Exit the function.
        sys.exit()

    # Iterate in the range.
    for i in range(l, arr[ind] // 2 + 1, 1):
        if (arr[ind] - i <= r):

            # Put the values in the respective
            # indices.
            brr[ind] = i
            brr[n - ind - 1] = arr[ind] - i

            # Call the function to find values for
            # other indices.
            brute(ind + 1, i, arr[ind] - i)

# Driver Code
if __name__ == '__main__':
    n = 2
    n *= 2

    arr[0] = 5
    arr[1] = 6
    INF64 = 1000000000000000000

    brute(0, 0, INF64)
```

### C#

```csharp
// C# program for the above approach
using System;
using System.Collections.Generic;

class GFG{

static int INF64 = (int)1e8;
static int N = 200 * 1000 + 13;

static int n;
static int[] arr = new int[N];
static int[] brr = new int[N];

// Function to find the possible
// output array
static void brute(int ind, int l, int r)
{

    // Base case for the recursion
    if (ind == n / 2)
    {

        // If ind becomes half of the size
        // then print the array.
        for(int i = 0; i < (int)n; i++)
            Console.Write(brr[i] + " ");

        // Exit the function.
        System.Environment.Exit(0);
    }

    // Iterate in the range.
    for(int i = l; i <= arr[ind] / 2; ++i)
        if (arr[ind] - i <= r)
        {

            // Put the values in the respective
            // indices.
            brr[ind] = i;
            brr[n - ind - 1] = arr[ind] - i;

            // Call the function to find values for
            // other indices.
            brute(ind + 1, i, arr[ind] - i);
        }
}

// Driver Code
public static void Main()
{
    n = 2;
    n *= 2;

    arr[0] = 5;
    arr[1] = 6;

    brute(0, 0, INF64);
}
}
```

# Java 描述语言

```javascript
<script>
    // JavaScript program for the above approach
    const `INF64` = 1000000000000000000;
    const `N` = 200 * 1000 + 13;

    let `n`;
    let `arr` = Array(`N`);
    let `brr` = Array(`N`);

    // Function to find the possible
    // output array
    function `brute`(`ind`, `l`, `r`)
    {
        // Base case for the recursion
        if (`ind` == `n` / 2)
        {
            // If ind becomes half of the size
            // then print the array.
            for (let `i` = 0; `i` < `n`; `i`++)
                `document.write`(`brr`[`i`] + " ");

            // Exit the function.
            `exit`(0);
        }

        // Iterate in the range.
        for (let `i` = `l`; `i` <= `arr`[`ind`] / 2; ++`i`)
            if (`arr`[`ind`] - `i` <= `r`)
            {
                // Put the values in the respective
                // indices.
                `brr`[`ind`] = `i`;
                `brr`[`n` - `ind` - 1] = `arr`[`ind`] - `i`;

                // Call the function to find values for
                // other indices.
                `brute`(`ind` + 1, `i`, `arr`[`ind`] - `i`);
            }
    }

    // Driver Code
    `n` = 2;
    `n` *= 2;

    `arr`[0] = 5;
    `arr`[1] = 6;

    `brute`(0, 0, `INF64`);

    // This code is contributed by Potta Lokesh
</script>
```

### Output

```
0 1 5 5
```

- **时间复杂度:** `O(N)`
- **辅助空间:** `O(N)`