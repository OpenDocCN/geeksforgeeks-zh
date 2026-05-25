# 重新排列数组，使得相同索引元素的总和为 K

> 原文: [https://www.geeksforgeeks.org/rearrange-array-such-that-sum-of-same-indexed-elements-is-atmost-k/](https://www.geeksforgeeks.org/rearrange-array-such-that-sum-of-same-indexed-elements-is-atmost-k/)

给定两个[数组](https://www.geeksforgeeks.org/introduction-to-arrays/) `A[]` 和 `B[]`，每个数组由 `N` 个整数和一个整数 `K` 组成，任务是重新排列数组 `B[]`，使得 `A_i + B_i` 的和至多为 `K`。如果不可能这样安排，打印 `-1`。

## 示例

> **输入:** `A[] = {1, 2, 3, 4, 2}`, `B[] = {1, 2, 3, 1, 1}`, `K = 5`
> **输出:** `1 3 1 2 1`
>
> **输入:** `A[] = {1, 2, 3, 4, 5}`, `B[] = {2, 3, 4, 5, 6}`, `K = 6`
> **输出:** `-1`

## 方法

满足给定条件的数组 `B[]` 的最优重排是[对数组进行降序排序](https://www.geeksforgeeks.org/how-to-sort-an-array-in-descending-order-using-stl-in-c/)。

## 证明

1.  因为每一对索引为 `i` 的元素之和至多为 `K`。因此，`Mn + num ≤ K` 且 `MX + num1 ≤ K`，其中 `Mn` 和 `MX` 分别是数组 `A[]` 和 `B[]` 中的最小值和最大值。
2.  因此，通过归纳法可以证明 `Mn` 和 `MX` 可以配对。
3.  因此，[将数组按降序排序](https://www.geeksforgeeks.org/different-ways-to-sort-an-array-in-descending-order-in-c-sharp/)是最优的重排方式。

## 按照以下步骤解决问题

*   [按降序排列数组 `B[]`](https://www.geeksforgeeks.org/sort-c-stl/)。
*   [遍历数组](https://www.geeksforgeeks.org/c-program-to-traverse-an-array/)，检查每一个索引 `i` 中，`A[i] + B[i]` 是否小于或等于 `K`。
*   如果任一对条件失败，打印 `-1`。
*   否则，[打印数组 `B[]`](https://www.geeksforgeeks.org/c-program-to-print-an-array-using-recursion/)。

下面是上述方法的实现：

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to rearrange array such
// that sum of similar indexed elements
// does not exceed K
void rearrangeArray(int A[], int B[],
                    int N, int K)
{
    // Sort the array B[]
    // in descending order
    sort(B, B + N, greater<int>());

    bool flag = true;

    for (int i = 0; i < N; i++) {

        // If condition fails
        if (A[i] + B[i] > K) {
            flag = false;
            break;
        }
    }

    if (!flag) {

        cout << "-1" << endl;
    }
    else {

        // Print the array
        for (int i = 0; i < N; i++) {
            cout << B[i] << " ";
        }
    }
}

// Driver Code
int main()
{
    // Given arrays
    int A[] = { 1, 2, 3, 4, 2 };
    int B[] = { 1, 2, 3, 1, 1 };

    int N = sizeof(A) / sizeof(A[0]);

    int K = 5;

    rearrangeArray(A, B, N, K);

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.util.*;

class GFG{

// Reverse array
static int[] reverse(int a[])
{
    int i, n = a.length, t;
    for(i = 0; i < n / 2; i++)
    {
        t = a[i];
        a[i] = a[n - i - 1];
        a[n - i - 1] = t;
    }
    return a;
}

// Function to rearrange array such
// that sum of similar indexed elements
// does not exceed K
static void rearrangeArray(int A[], int B[],
                           int N, int K)
{

    // Sort the array B[]
    // in descending order
    Arrays.sort(B);
    B = reverse(B);

    boolean flag = true;

    for(int i = 0; i < N; i++)
    {

        // If condition fails
        if (A[i] + B[i] > K)
        {
            flag = false;
            break;
        }
    }

    if (!flag)
    {
        System.out.print("-1" + "\n");
    }
    else
    {

        // Print the array
        for(int i = 0; i < N; i++)
        {
            System.out.print(B[i] + " ");
        }
    }
}

// Driver Code
public static void main(String[] args)
{

    // Given arrays
    int A[] = { 1, 2, 3, 4, 2 };
    int B[] = { 1, 2, 3, 1, 1 };

    int N = A.length;

    int K = 5;

    rearrangeArray(A, B, N, K);
}
}

// This code is contributed by Amit Katiyar
```

## Python 3

```python
# Python3 program for the above approach

# Function to rearrange array such
# that sum of similar indexed elements
# does not exceed K
def rearrangeArray(A, B, N, K):

    # Sort the array B[]
    # in descending order
    B.sort(reverse = True)

    flag = True

    for i in range(N):

        # If condition fails
        if (A[i] + B[i] > K):
            flag = False
            break

    if (flag == False):
        print("-1")
    else:

        # Print the array
        for i in range(N):
            print(B[i], end = " ")

# Driver Code
if __name__ == '__main__':

    # Given arrays
    A = [ 1, 2, 3, 4, 2 ]
    B = [ 1, 2, 3, 1, 1 ]

    N = len(A)
    K = 5;

    rearrangeArray(A, B, N, K)

# This code is contributed by SURENDRA_GANGWAR
```

## C#

```csharp
// C# program for the
// above approach
using System;
class GFG{

// Reverse array
static int[] reverse(int []a)
{
  int i, n = a.Length, t;

  for(i = 0; i < n / 2; i++)
  {
    t = a[i];
    a[i] = a[n - i - 1];
    a[n - i - 1] = t;
  }
  return a;
}

// Function to rearrange array such
// that sum of similar indexed elements
// does not exceed K
static void rearrangeArray(int []A, int []B,
                           int N, int K)
{   
  // Sort the array []B
  // in descending order
  Array.Sort(B);
  B = reverse(B);

  bool flag = true;

  for(int i = 0; i < N; i++)
  {
    // If condition fails
    if (A[i] + B[i] > K)
    {
      flag = false;
      break;
    }
  }

  if (!flag)
  {
    Console.Write("-1" + "\n");
  }
  else
  {
    // Print the array
    for(int i = 0; i < N; i++)
    {
      Console.Write(B[i] + " ");
    }
  }
}

// Driver Code
public static void Main(String[] args)
{   
  // Given arrays
  int []A = {1, 2, 3, 4, 2};
  int []B = {1, 2, 3, 1, 1};

  int N = A.Length;
  int K = 5;
  rearrangeArray(A, B, N, K);
}
}

// This code is contributed by Rajput-Ji
```

## JavaScript

```javascript
<script>
// JavaScript program for the above approach

// Reverse array
function reverse(a)
{
    let i, n = a.length, t;
    for(i = 0; i < n / 2; i++)
    {
        t = a[i];
        a[i] = a[n - i - 1];
        a[n - i - 1] = t;
    }
    return a;
}

// Function to rearrange array such
// that sum of similar indexed elements
// does not exceed K
function rearrangeArray(A, B, N, K)
{

    // Sort the array B[]
    // in descending order
    B.sort();
    B = reverse(B);

    let flag = true;

    for(let i = 0; i < N; i++)
    {

        // If condition fails
        if (A[i] + B[i] > K)
        {
            flag = false;
            break;
        }
    }

    if (!flag)
    {
         document.write("-1" + "<br/>");
    }
    else
    {

        // Print the array
        for(let i = 0; i < N; i++)
        {
             document.write(B[i] + " ");
        }
    }
}

// Driver Code

// Given arrays
let A = [ 1, 2, 3, 4, 2 ];
let B = [ 1, 2, 3, 1, 1 ];

let N = A.length;
let K = 5;

rearrangeArray(A, B, N, K);

// This code is contribute by target_2
</script>
```

**输出:**

```
3 2 1 1 1
```

**时间复杂度:** `O(N)`
**辅助空间复杂度:** `O(1)`