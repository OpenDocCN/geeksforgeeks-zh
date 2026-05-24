# 生成一个 N 长度数组，其和等于给定数组中相同索引元素的绝对差之和的两倍

> 原文: [https://www.geeksforgeeks.org/generate-an-n-length-array-with-sum-equal-to-twice-the-sum-of-its-absolute-difference-with-same-indexed-elements-of-given-array/](https://www.geeksforgeeks.org/generate-an-n-length-array-with-sum-equal-to-twice-the-sum-of-its-absolute-difference-with-same-indexed-elements-of-given-array/)

给定大小为 `N` 的数组 `arr[]`，任务是构建大小为 `N` 的数组 `brr[]`，满足以下条件:

*   在数组 `brr[]` 中的每对连续元素中，一个元素必须能被另一个元素整除，即 `brr[i]` 必须能被 `brr[i + 1]` 整除，反之亦然。
*   数组中的每个 `i` 元素 `brr[]` 必须满足 `brr[i] >= arr[i] / 2`。
*   数组 `arr[]` 元素的和必须大于或等于 `2 * ΣABS(arr[i] – brr[i])`。

**示例:**

> **输入:** `arr[] = { 11, 5, 7, 3, 2 }`
> **输出:** `8 4 4 2 2`
> **解释:**
> `ABS(11–8) + ABS(5–4) + ABS(7–4) + ABS(3–2) + ABS(2–2) = 8`
> `arr[0] + arr[1] + … + arr[4] = 28`
> `2 * 8 <= 28` 成立。
> 因此，`brr[]` 的可能值之一是 `8 4 4 2 2`。

> **输入:** `arr[] = { 11, 7, 5 }`
> **输出:** `{ 8, 4, 4 }`

## 方法

这个想法基于以下观察:

> 如果 `brr[i]` 是 2 的最近次幂，并且小于或等于 `arr[i]`，那么 `brr[i]` 必须大于或等于 `arr[i] / 2`，并且数组的元素之和 `arr[]` 必须大于或等于 `2 * ΣABS(arr[i] – brr[i])`。

按照以下步骤解决问题:

*   初始化一个数组 `brr[]`，存储满足给定条件的元素。
*   遍历数组 `arr[]`。对于每一个 `i` 元素，找到最近的小于或等于 `arr[i]` 的 2 的幂，存入 `brr[i]`。
*   最后，打印数组 `brr[]`。

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to construct an array
// with given conditions
void constructArray(int arr[], int N)
{
    int brr[N] = { 0 };

    // Traverse the array arr[]
    for (int i = 0; i < N; i++) {

        int K = log(arr[i]) / log(2);

        // Stores closest power of 2
        // less than or equal to arr[i]
        int R = pow(2, K);

        // Stores R into brr[i]
        brr[i] = R;
    }

    // Print array elements
    for (int i = 0; i < N; i++) {
        cout << brr[i] << " ";
    }
}

// Driver Code
int main()
{

    // Given array
    int arr[] = { 11, 5, 7, 3, 2 };

    // Size of the array
    int N = sizeof(arr) / sizeof(arr[0]);

    // Function Call
    constructArray(arr, N);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.util.*;

class GFG{

// Function to construct an array
// with given conditions
static void constructArray(int arr[], int N)
{
    int brr[] = new int[N];

    // Traverse the array arr[]
    for(int i = 0; i < N; i++)
    {
        int K = (int)(Math.log(arr[i]) /
                      Math.log(2));

        // Stores closest power of 2
        // less than or equal to arr[i]
        int R = (int)Math.pow(2, K);

        // Stores R into brr[i]
        brr[i] = R;
    }

    // Print array elements
    for(int i = 0; i < N; i++)
    {
        System.out.print(brr[i] + " ");
    }
}

// Driver Code
public static void main(String[] args)
{

    // Given array
    int arr[] = { 11, 5, 7, 3, 2 };

    // Size of the array
    int N = arr.length;

    // Function Call
    constructArray(arr, N);
}
}

// This code is contributed by 29AjayKumar
```

### Python 3

```python
# Python3 program for the above approach
from math import log

# Function to construct an array
# with given conditions
def constructArray(arr, N):
    brr = [0]*N

    # Traverse the array arr[]
    for i in range(N):
        K = int(log(arr[i])/log(2))

        # Stores closest power of 2
        # less than or equal to arr[i]
        R = pow(2, K)

        # Stores R into brr[i]
        brr[i] = R

    # Print array elements
    for i in range(N):
        print(brr[i], end = " ")

# Driver Code
if __name__ == '__main__':

    # Given array
    arr = [11, 5, 7, 3, 2]

    # Size of the array
    N = len(arr)

    # Function Call
    constructArray(arr, N)

# This code is contributed by mohit kumar 29
```

### C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to construct an array
// with given conditions
static void constructArray(int []arr, int N)
{
    int[] brr = new int[N];
    Array.Clear(brr, 0, brr.Length);

    // Traverse the array arr[]
    for(int i = 0; i < N; i++)
    {
        int K = (int)(Math.Log(arr[i]) /
                      Math.Log(2));

        // Stores closest power of 2
        // less than or equal to arr[i]
        int R = (int)Math.Pow(2, K);

        // Stores R into brr[i]
        brr[i] = R;
    }

    // Print array elements
    for(int i = 0; i < N; i++)
    {
        Console.Write(brr[i] + " ");
    }
}

// Driver Code
public static void Main()
{

    // Given array
    int []arr = { 11, 5, 7, 3, 2 };

    // Size of the array
    int N = arr.Length;

    // Function Call
    constructArray(arr, N);
}
}

// This code is contributed by SURENDRA_GANGWAR
```

### JavaScript

```javascript
<script>

// JavaScript program for the above approach

    // Function to construct an array
    // with given conditions
    function constructArray(arr , N) {
        var brr = Array(N).fill(0);

        // Traverse the array arr
        for (i = 0; i < N; i++) {
            var K = parseInt( (Math.log(arr[i]) / Math.log(2)));

            // Stores closest power of 2
            // less than or equal to arr[i]
            var R = parseInt( Math.pow(2, K));

            // Stores R into brr[i]
            brr[i] = R;
        }

        // Print array elements
        for (i = 0; i < N; i++) {
            document.write(brr[i] + " ");
        }
    }

    // Driver Code

        // Given array
        var arr = [ 11, 5, 7, 3, 2 ];

        // Size of the array
        var N = arr.length;

        // Function Call
        constructArray(arr, N);

// This code is contributed by todaysgaurav

</script>
```

**输出:**

```
8 4 4 2 2
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(N)`