# 将数组拆分为 K 长度的子集，以最小化每个子集的第二小元素之和

> 原文: [https://www.geeksforgeeks.org/split-array-into-k-length-subsets-to-minimize-sum-of-second-smallest-element-of-each-subset/](https://www.geeksforgeeks.org/split-array-into-k-length-subsets-to-minimize-sum-of-second-smallest-element-of-each-subset/)

给定一个大小为 `N` 的数组 `arr[]` 和一个整数 `K` (`N % K = 0`)，任务是将数组拆分为大小为 `K` 的子数组，使得每个子数组的第二小元素之和尽可能最小。

**示例:**

> **输入:** `arr[] = {11, 20, 5, 7, 8, 14, 2, 17, 16, 10}`, `K = 5`
> **输出:** 13
> **解释:** 将数组拆分为子集 `{11, 5, 14, 2, 10}` 和 `{20, 7, 8, 17, 16}` 生成第二小元素的最小和(= 5 + 8 = 13)。
>
> **输入:** `arr[] = {13, 19, 20, 5, 17, 11, 10, 8, 23, 14}`, `K = 5`
> **输出:** 19
> **解释:** 将数组拆分为子集 `{10, 19, 20, 11, 23}` 和 `{17, 5, 8, 13, 14}` 生成第二小元素的最小和(= 11 + 8 = 19)。

## 方法

问题可以通过排序技术解决。按照以下步骤解决此问题:

*   给定数组按升序排序。
*   由于所有子集都是长度为 `K` 的组，所以首先从索引 `1` 开始选择 `K` 个奇数索引元素，并计算它们的和。
*   打印得到的总和。

下面是上述方法的实现:

### C++

```cpp
// C++ implementation for above approach

#include <bits/stdc++.h>
using namespace std;

// Function to find the minimum sum of
// 2nd smallest elements of each subset
int findMinimum(int arr[], int N, int K)
{
    // Sort the array
    sort(arr, arr + N);

    // Stores minimum sum of second
    // elements of each subset
    int ans = 0;

    // Traverse first K 2nd smallest elements
    for (int i = 1; i < 2 * (N / K); i += 2) {

        // Update their sum
        ans += arr[i];
    }

    // Print the sum
    cout << ans;
}

// Driver Code
int main()
{
    // Given Array
    int arr[] = { 11, 20, 5, 7, 8,
                  14, 2, 17, 16, 10 };

    // Given size of the array
    int N = sizeof(arr)
            / sizeof(arr[0]);

    // Given subset lengths
    int K = 5;

    findMinimum(arr, N, K);

    return 0;
}
```

### Java

```java
// Java implementation for the above approach

import java.io.*;
import java.util.*;

class GFG {

    // Function to find the minimum sum of
    // 2nd smallest elements of each subset
    public static void findMinimum(
        int arr[], int N, int K)
    {
        // Sort the array
        Arrays.sort(arr);

        // Stores minimum sum of second
        // elements of each subset
        int ans = 0;

        // Traverse first K 2nd smallest elements
        for (int i = 1; i < 2 * (N / K); i += 2) {

            // Update their sum
            ans += arr[i];
        }

        // Print the sum
        System.out.println(ans);
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Given Array
        int[] arr = { 11, 20, 5, 7, 8,
                      14, 2, 17, 16, 10 };

        // Given length of array
        int N = arr.length;

        // Given subset lengths
        int K = 5;

        findMinimum(arr, N, K);
    }
}
```

### Python 3

```python
# Python3 implementation for above approach

# Function to find the minimum sum of
# 2nd smallest elements of each subset
def findMinimum(arr, N, K):

    # Sort the array
    arr = sorted(arr)

    # Stores minimum sum of second
    # elements of each subset
    ans = 0

    # Traverse first K 2nd smallest elements
    for i in range(1, 2 * (N//K), 2):

        # Update their sum
        ans += arr[i]

    # Print the sum
    print (ans)

# Driver Code
if __name__ == '__main__':

    # Given Array
    arr = [11, 20, 5, 7, 8, 14, 2, 17, 16, 10]

    # Given size of the array
    N = len(arr)

    # Given subset lengths
    K = 5
    findMinimum(arr, N, K)

# This code is contributed by mohit kumar 29
```

### C#

```csharp
// C# implementation for above approach
using System;

class GFG{

// Function to find the minimum sum of
// 2nd smallest elements of each subset
public static void findMinimum(int[] arr, int N,
                               int K)
{

    // Sort the array
    Array.Sort(arr);

    // Stores minimum sum of second
    // elements of each subset
    int ans = 0;

    // Traverse first K 2nd smallest elements
    for(int i = 1; i < 2 * (N / K); i += 2)
    {

        // Update their sum
        ans += arr[i];
    }

    // Print the sum
    Console.WriteLine(ans);
}

// Driver Code
public static void Main()
{

    // Given Array
    int[] arr = { 11, 20, 5, 7, 8,
                  14, 2, 17, 16, 10 };

    // Given length of array
    int N = arr.Length;

    // Given subset lengths
    int K = 5;

    findMinimum(arr, N, K);
}
}

// This code is contributed by susmitakundugoaldanga
```

### JavaScript

```javascript
<script>

// Javascript implementation for
// the above approach

    // Function to find the minimum sum of
    // 2nd smallest elements of each subset
    function findMinimum(arr , N , K)
    {
        // Sort the array
        arr.sort((a,b)=>a-b);

        // Stores minimum sum of second
        // elements of each subset
        var ans = 0;

        // Traverse first K 2nd smallest elements
        for (i = 1; i < 2 * (parseInt(N / K)); i += 2)
        {

            // Update their sum
            ans += arr[i];
        }

        // Print the sum
        document.write(ans);
    }

    // Driver Code

        // Given Array
        var arr = [ 11, 20, 5, 7, 8, 14, 2, 17, 16, 10 ];

        // Given length of array
        var N = arr.length;

        // Given subset lengths
        var K = 5;

        findMinimum(arr, N, K);

// This code is contributed by todaysgaurav

</script>
```

**Output:**

时间复杂度: O(NlogN)
空间复杂度: O(N)