# D 的最小可能值，当与 K 相加或相减时，重复获得每个数组元素

> 原文: [https://www.geeksforgeeks.org/minimum-possible-value-of-d-which-when-added-to-or-subtracted-from-k-repeatedly-obtains-every-array-element/](https://www.geeksforgeeks.org/minimum-possible-value-of-d-which-when-added-to-or-subtracted-from-k-repeatedly-obtains-every-array-element/)

给定一个大小为 `N` 的数组 `arr[]` 和一个整数 `K`，任务是找到 `D` 的最大可能值，这样就可以从 `K` 的初始值开始，通过在每一步将 `K` 改为 `K - D` 或 `K + D` 获得每个数组元素。

**示例:**

> **输入:** `arr[] = {1, 7, 11}`，`K = 3`
> **输出:** `2`
> **说明:**
> 考虑到 `D` 的值为 `2`，每个数组元素都可以通过以下运算得到:
> *   `arr[0](= 1)`: 从 `K(=3)` 递减 `2` 得到 `arr[0]`。
> *   `arr[1](= 7)`: 将 `K(=3)` 增加 `2` 倍 `D` 得到 `arr[1]`。
> *   `arr[2](= 11)`: 将 `K(=3)` 增加 `4` 倍 `D` 得到 `arr[2]`。
> 因此，`D (=2)` 满足条件。还有，就是 `D` 的最大可能值。

> **输入:** `arr[] = {33, 105, 57}`，`K = 81`
> **输出:** `24`

**逼近:** 求各数组元素与 `K` 的绝对差的最大公约数即可解决问题，按照以下步骤解决问题:
*   遍历数组 `arr[]`，并将当前元素 `arr[i]` 的值更改为 `ABS(arr[i] - K)`。
*   初始化一个变量，比如 `D`，为 `arr[0]`，存储结果。
*   使用变量 `i` 在范围 `[1, N-1]` 中迭代，并且在每次迭代中，将 `D` 的值更新为 `gcd(D, arr[i])`。
*   完成以上步骤后，打印 `D` 的值作为答案。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Recursive function to find
// previous gcd of a and b
int gcd(int a, int b)
{
    if (b == 0)
        return a;

    return gcd(b, a % b);
}

// Function to find the maximum value
// of D such that every element in
// the array can be obtained by
// performing K + D or K - D
int findMaxD(int arr[], int N, int K)
{
    // Traverse the array arr[]
    for (int i = 0; i < N; i++) {

        // Update arr[i]
        arr[i] = abs(arr[i] - K);
    }

    // Stores GCD of the array
    int D = arr[0];

    // Iterate over the range [1, N]
    for (int i = 1; i < N; i++) {

        // Update the value of D
        D = gcd(D, arr[i]);
    }

    // Print the value of D
    return D;
}

// Driver Code
int main()
{

    int arr[] = { 1, 7, 11 };
    int N = sizeof(arr) / sizeof(arr[0]);
    int K = 3;

    cout << findMaxD(arr, N, K);
    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.io.*;

class GFG{

// Recursive function to find
// previous gcd of a and b
static int gcd(int a, int b)
{
    if (b == 0)
        return a;

    return gcd(b, a % b);
}

// Function to find the maximum value
// of D such that every element in
// the array can be obtained by
// performing K + D or K - D
static int findMaxD(int arr[], int N, int K)
{

    // Traverse the array arr[]
    for(int i = 0; i < N; i++)
    {

        // Update arr[i]
        arr[i] = Math.abs(arr[i] - K);
    }

    // Stores GCD of the array
    int D = arr[0];

    // Iterate over the range [1, N]
    for(int i = 1; i < N; i++)
    {

        // Update the value of D
        D = gcd(D, arr[i]);
    }

    // Print the value of D
    return D;
}

// Driver Code
public static void main(String[] args)
{
    int arr[] = { 1, 7, 11 };
    int N = arr.length;
    int K = 3;

    System.out.print(findMaxD(arr, N, K));
}
}

// This code is contributed by rishavmahato348
```

## Python 3

```python
# // python program for the above approach

# // Recursive function to find
# // previous gcd of a and b
def gcd(a, b):
    if (b == 0):
        return a
    return gcd(b, a % b)

# // Function to find the maximum value
# // of D such that every element in
# // the array can be obtained by
# // performing K + D or K - D
def findMaxD(arr, N, K):

    # // Traverse the array arr[]
    for i in range(0, N):

        # // Update arr[i]
        arr[i] = abs(arr[i] - K)

    # // Stores GCD of the array
    D = arr[0]

    # // Iterate over the range[1, N]
    for i in range(1, N):

        # // Update the value of D
        D = gcd(D, arr[i])

    # // Print the value of D
    return D

# // Driver Code
arr = [1, 7, 11]
N = len(arr)
K = 3
print(findMaxD(arr, N, K))

# This code is contributed by amreshkumar3
```

## C#

```csharp
// C# program for the above approach
using System;

class GFG {

    // Recursive function to find
    // previous gcd of a and b
    static int gcd(int a, int b)
    {
        if (b == 0)
            return a;

        return gcd(b, a % b);
    }

    // Function to find the maximum value
    // of D such that every element in
    // the array can be obtained by
    // performing K + D or K - D
    static int findMaxD(int[] arr, int N, int K)
    {

        // Traverse the array arr[]
        for (int i = 0; i < N; i++) {

            // Update arr[i]
            arr[i] = Math.Abs(arr[i] - K);
        }

        // Stores GCD of the array
        int D = arr[0];

        // Iterate over the range [1, N]
        for (int i = 1; i < N; i++) {

            // Update the value of D
            D = gcd(D, arr[i]);
        }

        // Print the value of D
        return D;
    }

    // Driver Code
    public static void Main()
    {
        int[] arr = { 1, 7, 11 };
        int N = arr.Length;
        int K = 3;

        Console.Write(findMaxD(arr, N, K));
    }
}

// This code is contributed by subhammahato348.
```

## JavaScript

```javascript
<script>
// Javascript program for the above approach

// Recursive function to find
// previous gcd of a and b
function gcd(a, b) {
    if (b == 0)
        return a;

    return gcd(b, a % b);
}

// Function to find the maximum value
// of D such that every element in
// the array can be obtained by
// performing K + D or K - D
function findMaxD(arr, N, K) {
    // Traverse the array arr[]
    for (let i = 0; i < N; i++) {

        // Update arr[i]
        arr[i] = Math.abs(arr[i] - K);
    }

    // Stores GCD of the array
    let D = arr[0];

    // Iterate over the range [1, N]
    for (let i = 1; i < N; i++) {

        // Update the value of D
        D = gcd(D, arr[i]);
    }

    // Print the value of D
    return D;
}

// Driver Code

let arr = [1, 7, 11];
let N = arr.length;
let K = 3;

document.write(findMaxD(arr, N, K));

// This code is contributed by _saurabh_jaiswal.
</script>
```

**Output**

```
2
```

**时间复杂度:** `O(N*log(N))`
**辅助空间:** `O(1)`