# 生成左右各数组元素出现次数不同的数组

> 原文：[https://www.geeksforgeeks.org/generate-array-having-differences-between-count-of-occurrences-of-every-array-element-on-its-left-and-right/](https://www.geeksforgeeks.org/generate-array-having-differences-between-count-of-occurrences-of-every-array-element-on-its-left-and-right/)

给定一个由 `N` 个整数组成的数组 `A[]`，任务是构建一个数组 `B[]` 使得对于每一个 `i` 索引，`B[i] = X - Y`，其中 `X` 和 `Y` 是 `A[i]` 在其前后的出现次数。

## 示例

> **输入:** `A[] = {3, 2, 1, 2, 3}`
> **输出:** `1 1 0 -1 -1`
> **解释:**
> `arr[0] = 3`，`X = 1`，`Y = 0`。因此，打印 `1`。
> `arr[1] = 2`，`X = 1`，`Y = 0`。因此，打印 `1`。
> `arr[2] = 1`，`X = 0`，`Y = 0`。因此，打印 `0`。
> `arr[3] = 2`，`X = 0`，`Y = 1`。因此，打印 `-1`。
> `arr[4] = 3`，`X = 0`，`Y = 1`。因此，打印 `-1`。

> **输入:** `A[] = {1, 2, 3, 4, 5}`
> **输出:** `0 0 0 0 0`

## 天真法

解决问题最简单的方法就是遍历数组，考虑每个数组元素，并与它左右两边的所有元素进行比较。对于每个数组元素，在它的左侧和右侧打印其出现次数的差异。

**时间复杂度:** `O(N^2)`
**辅助空间:** `O(1)`

## 高效方法

按照以下步骤优化上述方法：

1.  初始化两个数组 `left[]` 和 `right[]`，以存储出现在每个数组元素的左右索引上的数组元素的频率。
2.  计算左右累计频率表。
3.  打印两个频率数组中相同索引元素的差异。

下面是上述方法的实现：

### C++

```cpp
// C++ program of the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to construct array of
// differences of counts on the left
// and right of the given array
void constructArray(int A[], int N)
{
    // Initialize left and right
    // frequency arrays
    int left[N + 1] = { 0 };
    int right[N + 1] = { 0 };
    int X[N + 1] = { 0 }, Y[N + 1] = { 0 };

    // Construct left cumulative
    // frequency table
    for (int i = 0; i < N; i++) {
        X[i] = left[A[i]];
        left[A[i]]++;
    }

    // Construct right cumulative
    // frequency table
    for (int i = N - 1; i >= 0; i--) {
        Y[i] = right[A[i]];
        right[A[i]]++;
    }

    // Print the result
    for (int i = 0; i < N; i++) {
        cout << Y[i] - X[i] << " ";
    }
}

// Driver Code
int main()
{
    int A[] = { 3, 2, 1, 2, 3 };
    int N = sizeof(A) / sizeof(A[0]);

    // Function Call
    constructArray(A, N);

    return 0;
}
```

### Java

```java
// Java program of the above approach
import java.io.*;

class GFG{

// Function to construct array of
// differences of counts on the left
// and right of the given array
static void constructArray(int A[], int N)
{

    // Initialize left and right
    // frequency arrays
    int[] left = new int[N + 1];
    int[] right = new int[N + 1];
    int[] X = new int[N + 1];
    int[] Y = new int[N + 1];

    // Construct left cumulative
    // frequency table
    for(int i = 0; i < N; i++)
    {
        X[i] = left[A[i]];
        left[A[i]]++;
    }

    // Construct right cumulative
    // frequency table
    for(int i = N - 1; i >= 0; i--)
    {
        Y[i] = right[A[i]];
        right[A[i]]++;
    }

    // Print the result
    for (int i = 0; i < N; i++)
    {
        System.out.print(Y[i] - X[i] + " ");
    }
}

// Driver Code
public static void main(String[] args)
{
    int A[] = { 3, 2, 1, 2, 3 };
    int N = A.length;

    // Function Call
    constructArray(A, N);
}
}

// This code is contributed by akhilsaini
```

### Python 3

```python
# Python3 program of the above approach

# Function to construct array of
# differences of counts on the left
# and right of the given array
def constructArray(A, N):

    # Initialize left and right
    # frequency arrays
    left = [0] * (N + 1)
    right = [0] * (N + 1)
    X = [0] * (N + 1)
    Y = [0] * (N + 1)

    # Construct left cumulative
    # frequency table
    for i in range(0, N):
        X[i] = left[A[i]]
        left[A[i]] += 1

    # Construct right cumulative
    # frequency table
    for i in range(N - 1, -1, -1):
        Y[i] = right[A[i]]
        right[A[i]] += 1

    # Print the result
    for i in range(0, N):
        print(Y[i] - X[i], end = " ")

# Driver Code
if __name__ == '__main__':

    A = [ 3, 2, 1, 2, 3 ]
    N = len(A)

    # Function Call
    constructArray(A, N)

# This code is contributed by akhilsaini
```

### C#

```csharp
// C# program of the above approach
using System;

class GFG{

// Function to construct array of
// differences of counts on the left
// and right of the given array
static void constructArray(int[] A, int N)
{

    // Initialize left and right
    // frequency arrays
    int[] left = new int[N + 1];
    int[] right = new int[N + 1];
    int[] X = new int[N + 1];
    int[] Y = new int[N + 1];

    // Construct left cumulative
    // frequency table
    for(int i = 0; i < N; i++)
    {
        X[i] = left[A[i]];
        left[A[i]]++;
    }

    // Construct right cumulative
    // frequency table
    for(int i = N - 1; i >= 0; i--)
    {
        Y[i] = right[A[i]];
        right[A[i]]++;
    }

    // Print the result
    for(int i = 0; i < N; i++)
    {
        Console.Write(Y[i] - X[i] + " ");
    }
}

// Driver Code
public static void Main()
{
    int[] A = { 3, 2, 1, 2, 3 };
    int N = A.Length;

    // Function Call
    constructArray(A, N);
}
}

// This code is contributed by akhilsaini
```

### JavaScript

```javascript
<script>

// JavaScript program of the above approach

// Function to construct array of
// differences of counts on the left
// and right of the given array
function constructArray(A, N)
{

    // Initialize left and right
    // frequency arrays
    let left = [];
    let right = [];
    let X = [];
    let Y = [];

    for(let i = 0; i < N; i++)
    {
        X[i] = 0;
        left[i] = 0;
        right[i] = 0;
        Y[i]= 0;
    }

    // Construct left cumulative
    // frequency table
    for(let i = 0; i < N; i++)
    {
        X[i] = left[A[i]];
        left[A[i]]++;
    }

    // Construct right cumulative
    // frequency table
    for(let i = N - 1; i >= 0; i--)
    {
        Y[i] = right[A[i]];
        right[A[i]]++;
    }

    // Print the result
    for(let i = 0; i < N; i++)
    {
        document.write(Y[i] - X[i] + " ");
    }
}

// Driver Code
let A = [ 3, 2, 1, 2, 3 ];
let N = A.length;

// Function Call
constructArray(A, N);

// This code is contribute by target_2

</script>
```

**输出:**

```
1 1 0 -1 -1
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(N)`