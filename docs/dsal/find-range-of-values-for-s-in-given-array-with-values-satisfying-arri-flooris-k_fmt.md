# 找出给定数组中 S 的取值范围，取值满足 `arr[i] = floor((i*S)/K)`

> 原文: [https://www.geeksforgeeks.org/find-range-of-values-for-s-in-given-array-with-values-satisfying-arri-flooris-k/](https://www.geeksforgeeks.org/find-range-of-values-for-s-in-given-array-with-values-satisfying-arri-flooris-k/)

给定一个由 `N` 个正整数和一个正整数 `K` 组成的数组 `arr[]`，任务是找到范围 `[L, R]`，对于该范围内的所有元素，假设 `S` 每个数组元素 `arr[i]` 为 `floor((i*S)/K)`。

**示例:**

> **输入:** `N = 5`，`K = 10`，`arr[] = {2, 4, 6, 9, 11}`
> **输出:** `23 23`
> **解释:**
> 当 `S = 23` 时，在等式中代入给出相同的数组值:
> `arr[1]= floor((1 * 23)/10)= 2`
> `arr[2]= floor((2 * 23/10))= 4`
> `arr[3]` ...
>
> **输入:** `N = 5`，`K = 100`，`arr[] = {0, 0, 0, 0, 1}`
> **输出:** `20 24`

**方法:** 按照以下步骤解决给定问题:

*   将两个变量 `L` 和 `R` 初始化为分别存储左范围和右范围值的 `INT_MIN` 和 `INT_MAX`。
*   遍历给定数组 `arr[]`，并执行以下步骤:
    *   将第 `i` 个数组元素的左侧范围的可能值作为上限 `(1.0*arr[i]*K/(i + 1))`。
    *   为第 `i` 个数组元素找到正确范围的可能值作为上限 `((1.0+arr[i])* K/(i+1))–1`。
    *   将 `L` 的值更新为 `max(L, l)`，将 `R` 的值更新为 `min(R, r)`。
*   完成上述步骤后，打印 `L` 和 `R` 的值作为结果范围。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the range of values
// for S in a given array that satisfies
// the given condition
void findRange(int arr[], int N, int K)
{

    // Stores the left range value
    int L = INT_MIN;

    // Stores the right range value
    int R = INT_MAX;

    for (int i = 0; i < N; i++) {
        // Find the current left range
        // value for S
        int l = (int)ceil(1.0 * arr[i] * K / (i + 1));

        // Find the current right range
        // value for S
        int r = (int)ceil((1.0 + arr[i]) * K / (i + 1)) - 1;

        // Updating L value
        L = max(L, l);

        // Updating R value
        R = min(R, r);
    }

    cout << L << " " << R;
}

// Driver Code
int main()
{

    int arr[] = { 2, 4, 6, 9, 11 };
    int K = 10;
    int N = sizeof(arr) / sizeof(int);

    findRange(arr, N, K);
    return 0;
}

// This code is contributed by Potta Lokesh
```

## Java

```java
// Java program for the above approach

import java.util.*;
import java.lang.*;

class Codechef {

    // Function to find the range of values
    // for S in a given array that satisfies
    // the given condition
    static void findRange(int arr[], int N,
                          int K)
    {

        // Stores the left range value
        int L = Integer.MIN_VALUE;

        // Stores the right range value
        int R = Integer.MAX_VALUE;

        for (int i = 0; i < N; i++) {
            // Find the current left range
            // value for S
            int l = (int)Math.ceil(
                1.0 * arr[i] * K / (i + 1));

            // Find the current right range
            // value for S
            int r = (int)Math.ceil(
                        (1.0 + arr[i]) * K / (i + 1))
                    - 1;

            // Updating L value
            L = Math.max(L, l);

            // Updating R value
            R = Math.min(R, r);
        }

        System.out.println(L + " " + R);
    }

    // Driver Code
    public static void main(String[] args)
    {
        int arr[] = { 2, 4, 6, 9, 11 };
        int K = 10;
        int N = arr.length;

        findRange(arr, N, K);
    }
}
```

## Python 3

```python
# Python 3 program for the above approach
from math import ceil,floor
import sys

# Function to find the range of values
# for S in a given array that satisfies
# the given condition
def findRange(arr, N, K):

    # Stores the left range value
    L = -sys.maxsize-1

    # Stores the right range value
    R = sys.maxsize

    for i in range(N):

        # Find the current left range
        # value for S
        l = ceil(1.0 * arr[i] * K / (i + 1))

        # Find the current right range
        # value for S
        r = ceil((1.0 + arr[i]) * K / (i + 1) - 1)

        # Updating L value
        L = max(L, l)

        # Updating R value
        R = min(R, r)

    print(L,R)

# Driver Code
if __name__ == '__main__':
    arr = [2, 4, 6, 9, 11]
    K = 10
    N = len(arr)
    findRange(arr, N, K)

    # This code is contributed by SURENDRA_GANGWAR.
```

## C#

```csharp
// C# program for the above approach

using System;

class GFG {

    // Function to find the range of values
    // for S in a given array that satisfies
    // the given condition
    static void findRange(int[] arr, int N, int K)
    {

        // Stores the left range value
        int L = Int32.MinValue;

        // Stores the right range value
        int R = Int32.MaxValue;

        for (int i = 0; i < N; i++)
        {

            // Find the current left range
            // value for S
            int l = (int)Math.Ceiling(1.0 * arr[i] * K
                                      / (i + 1));

            // Find the current right range
            // value for S
            int r = (int)Math.Ceiling((1.0 + arr[i]) * K
                                      / (i + 1))
                    - 1;

            // Updating L value
            L = Math.Max(L, l);

            // Updating R value
            R = Math.Min(R, r);
        }

        Console.WriteLine(L + " " + R);
    }

    // Driver Code
    public static void Main()
    {
        int[] arr = { 2, 4, 6, 9, 11 };
        int K = 10;
        int N = arr.Length;

        findRange(arr, N, K);
    }
}

// This code is contributed by subham348.
```

## JavaScript

```javascript
<script>
// JavaScript program for the above approach

// Function to find the range of values
// for S in a given array that satisfies
// the given condition
function findRange(arr, N, K)
{

    // Stores the left range value
    let L = Number.MIN_VALUE;

    // Stores the right range value
    let R = Number.MAX_VALUE;

    for (let i = 0; i < N; i++) {
        // Find the current left range
        // value for S
        let l = Math.ceil(1.0 * arr[i] * K / (i + 1));

        // Find the current right range
        // value for S
        let r = Math.ceil((1.0 + arr[i]) * K / (i + 1)) - 1;

        // Updating L value
        L = Math.max(L, l);

        // Updating R value
        R = Math.min(R, r);
    }

    document.write(L + " " + R);
}

    // Driver code
    let arr = [ 2, 4, 6, 9, 11 ];
    let K = 10;
    let N = arr.length;

    findRange(arr, N, K);

// This code is contributed by AnkThon
</script>
```

**输出:**

```
23 23
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`