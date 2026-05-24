# Geek-onacci 编号

> 原文: [https://www.geeksforgeeks.org/geek-onacci-number/](https://www.geeksforgeeks.org/geek-onacci-number/)

给定四个整数 `A`、`B`、`C` 和 `N`，其中 `A`、`B`、`C` 代表奇客纳奇数列的前三个数字，任务是找到奇客纳奇数列的第 `N` 项。

> 极客纳奇数列的第 `N` 项是该数列中其前三项的和，即第 `(N–1)` 项、`(N–2)` 项和第 `(N–3)` 项极客纳奇数之和。

## 示例

> **输入:** `A = 1`，`B = 3`，`C = 2`，`N = 4`
> **输出:** `6`
> **说明:** 极客纳奇数列为 `1`，`3`，`2`，`6`，`11`，`19`，…
> 因此，第 `4` 个极客纳奇数为 `6`。
>
> **输入:** `A = 1`，`B = 3`，`C = 2`，`N = 6`
> **输出:** `19`

## 方法

给定的问题可以通过生成直到 `N` 项的 geekonacci 数列并打印得到的数列的第 `N` 项来解决。按照以下步骤解决此问题:

*   初始化一个大小为 `N` 的[数组](https://www.geeksforgeeks.org/introduction-to-arrays/) `arr[]`，并初始化 `arr[0] = A`，`arr[1] = B`，以及 `arr[2] = C`。
*   迭代范围 `[3，N–1]` 并更新每一个第 `i` 元素的值，即 `arr[i]` 为 `(arr[i–1] + arr[i–2] + arr[i–3])` 得到奇客纳奇数列的第 `i` 项。
*   完成上述步骤后，将 `arr[N–1]` 的值打印为 geekonacci 数列的结果第 `N` 号。

下面是上述方法的实现:

## C++

```cpp
#include <bits/stdc++.h>
using namespace std;

// Function to calculate the
// N-th Geek-onacci Number
int find(int A, int B,
                int C, int N)
{

    // Stores the geekonacci series
    int arr[N];

    // Store the first three
    // terms of the series
    arr[0] = A;
    arr[1] = B;
    arr[2] = C;

    // Iterate over the range [3, N]
    for (int i = 3; i < N; i++) {

        // Update the value of arr[i]
        // as the sum of previous 3
        // terms in the series
        arr[i] = arr[i - 1]
                 + arr[i - 2]
                 + arr[i - 3];
    }

    // Return the last element
    // of arr[] as the N-th term
    return arr[N - 1];
}

// Driver Code
int main()
{
  int A = 1, B = 3, C = 2, N = 4;
  cout<<(find(A, B, C, N));

  return 0;
}

// This code is contributed by mohit kumar 29.
```

## Java

```java
// Java program for the above approach

import java.io.*;
import java.lang.*;
import java.util.*;

class GFG {

    // Function to calculate the
    // N-th Geek-onacci Number
    static int find(int A, int B,
                    int C, int N)
    {
        // Stores the geekonacci series
        int[] arr = new int[N];

        // Store the first three
        // terms of the series
        arr[0] = A;
        arr[1] = B;
        arr[2] = C;

        // Iterate over the range [3, N]
        for (int i = 3; i < N; i++) {

            // Update the value of arr[i]
            // as the sum of previous 3
            // terms in the series
            arr[i] = arr[i - 1]
                     + arr[i - 2]
                     + arr[i - 3];
        }

        // Return the last element
        // of arr[] as the N-th term
        return arr[N - 1];
    }

    // Driver Code
    public static void main(String[] args)
    {
        int A = 1, B = 3, C = 2, N = 4;
        System.out.print(find(A, B, C, N));
    }
}
```

## Python 3

```python
# Python3 program for the above approach

# Function to calculate the
# N-th Geek-onacci Number
def find(A, B, C, N) :

    # Stores the geekonacci series
    arr = [0] * N

    # Store the first three
    # terms of the series
    arr[0] = A
    arr[1] = B
    arr[2] = C

    # Iterate over the range [3, N]
    for i in range(3, N):

        # Update the value of arr[i]
        # as the sum of previous 3
        # terms in the series
        arr[i] = (arr[i - 1]
                 + arr[i - 2]
                 + arr[i - 3])

    # Return the last element
    # of arr[] as the N-th term
    return arr[N - 1]

# Driver Code
A = 1
B = 3
C = 2
N = 4

print(find(A, B, C, N))

# This code is contributed by sanjoy_62.
```

## C#

```csharp
// C# program for the above approach
using System;

class GFG{

  // Function to calculate the
  // N-th Geek-onacci Number
  static int find(int A, int B,
                  int C, int N)
  {
    // Stores the geekonacci series
    int[] arr = new int[N];

    // Store the first three
    // terms of the series
    arr[0] = A;
    arr[1] = B;
    arr[2] = C;

    // Iterate over the range [3, N]
    for (int i = 3; i < N; i++) {

      // Update the value of arr[i]
      // as the sum of previous 3
      // terms in the series
      arr[i] = arr[i - 1]
        + arr[i - 2]
        + arr[i - 3];
    }

    // Return the last element
    // of arr[] as the N-th term
    return arr[N - 1];
  }

  // Driver Code
  public static void Main(string[] args)
  {
    int A = 1, B = 3, C = 2, N = 4;
    Console.Write(find(A, B, C, N));
  }
}

// This code is contributed by code_hunt.
```

## JavaScript

```javascript
<script>

// Javascript program for the above approach

    // Function to calculate the
    // N-th Geek-onacci Number
    function find(A, B, C, N)
    {
        // Stores the geekonacci series
        let arr = new Array(N).fill(0);

        // Store the first three
        // terms of the series
        arr[0] = A;
        arr[1] = B;
        arr[2] = C;

        // Iterate over the range [3, N]
        for (let i = 3; i < N; i++) {

            // Update the value of arr[i]
            // as the sum of previous 3
            // terms in the series
            arr[i] = arr[i - 1]
                     + arr[i - 2]
                     + arr[i - 3];
        }

        // Return the last element
        // of arr[] as the N-th term
        return arr[N - 1];
    }

// Driver code

    let A = 1, B = 3, C = 2, N = 4;
    document.write(find(A, B, C, N));

</script>
```

**输出:**

```
6
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(N)`