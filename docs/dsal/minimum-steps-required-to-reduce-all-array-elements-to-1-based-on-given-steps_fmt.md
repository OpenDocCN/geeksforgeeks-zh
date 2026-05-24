# 根据给定步骤将所有阵列元素减少到1所需的最小步骤

> 原文：[https://www.geeksforgeeks.org/minimum-steps-required-to-reduce-all-array-elements-to-1-based-on-given-steps/](https://www.geeksforgeeks.org/minimum-steps-required-to-reduce-all-array-elements-to-1-based-on-given-steps/)

给定一个大小为`N`的数组`arr`。任务是找到将所有数组元素减少到1所需的**最小**步数。在每个步骤中，执行以下给定操作：

*   选择任意一个起始索引，比如`i`，跳转到第`(arr[i] + i)`个索引，将其减少1，同时将第`(arr[i] + i)`个索引减少1个，继续这个过程，直到到达数组的末尾。
*   如果一个元素已经减为1，不能再减了，还是一样。

**示例：**

> **输入：** `arr[] = {4, 2, 3, 2, 2, 2, 1, 2}`，`N = 8`
> **输出：** 5
> **说明：** 系列操作可以通过以下方式进行：
> *   `{4, 2, 3, 2, 2, 2, 1, 2}`，减量值为1，`arr[] = {4, 2, 2, 2, 2, 1, 1, 1}`
> *   `{4, 2, 2, 2, 2, 1, 1, 1}`，减量值为1，`arr[] = {3, 2, 2, 2, 1, 1, 1, 1}`
> *   `{3, 2, 2, 2, 1, 1, 1, 1}`，减量值为1，`arr[] = {2, 2, 2, 1, 1, 1, 1, 1}`
> *   `{2, 2, 2, 1, 1, 1, 1, 1}`，减量值为1，`arr[] = {1, 2, 1, 1, 1, 1, 1, 1}`
> *   `{1, 2, 1, 1, 1, 1, 1, 1}`，减量值为1，`arr[] = {1, 1, 1, 1, 1, 1, 1, 1}`
>
> 因此，所需步骤总数= 5

> **输入：** `arr[] = {1, 3, 1, 2, 2}`，`N = 5`
> **输出：** 2

## 方法

给定的问题可以通过将问题分成4个部分来解决：`(0 到 i-1)` | `i` | `(i+1)` | `(i+2 到 n–1)`。按照以下步骤解决问题：

1.  取一个向量，比如`v`，表示一个元素由于访问前面的元素而减少了多少次。
2.  `v`中的每个元素`v[i]`表示`arr[i]`中由于访问从`0`到`(i-1)`的元素而减少的计数。
3.  迭代数组`arr[]`，在使`0`到`(i-1)`个元素等于1之后，取一个变量`k`来存储由于元素`arr[i]`而必须在答案中添加的遍数。
4.  在循环中，运行另一个循环（即第二个循环）来计算当前元素`arr[i]`影响`(i+2)`到`N`元素（访问第i个元素后减少）的次数。

下面是上述方法的实现：

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find minimum steps
// required to reduce all array
// elements to 1
int minSteps(int arr[], int N)
{
    // Variable to store the answer
    int steps = 0;

    // Vector with all elements initialized
    // with 0
    vector<long long> v(N + 1, 0);

    // Traverse the array
    for (int i = 0; i < N; ++i) {
        // Variable to store the numbers of
        // passes that have to add in answer
        // due to element arr[i] after making
        // 0 to (i-1) elements equal to 1
        int k = max(0ll, arr[i] - 1 - v[i]);

        // Increment steps by K
        steps += k;
        // Update element in v
        v[i] += k;

        // Loop to compute how much current element
        // effect the (i+2) to N elements
        for (int j = i + 2; j <= min(i + arr[i], N); j++) {
            v[j]++;
        }
        v[i + 1] += v[i] - arr[i] + 1;
    }
    // Return steps which is the answer
    return steps;
}

// Driver Code
int main()
{
    int arr[] = { 4, 2, 3, 2, 2, 2, 1, 2 };
    int N = sizeof(arr) / sizeof(arr[0]);

    cout << minSteps(arr, N);

    return 0;
}
```

### Java

```java
// Java code for the above approach
import java.io.*;

class GFG
{

    // Function to find minimum steps
    // required to reduce all array
    // elements to 1
    static int minSteps(int arr[], int N)
    {

        // Variable to store the answer
        int steps = 0;

        // Vector with all elements initialized
        // with 0
        int v[] = new int[N + 1];

        // Traverse the array
        for (int i = 0; i < N; ++i)
        {

            // Variable to store the numbers of
            // passes that have to add in answer
            // due to element arr[i] after making
            // 0 to (i-1) elements equal to 1
            int k = Math.max(0, arr[i] - 1 - v[i]);

            // Increment steps by K
            steps += k;
            // Update element in v
            v[i] += k;

            // Loop to compute how much current element
            // effect the (i+2) to N elements
            for (int j = i + 2;
                 j <= Math.min(i + arr[i], N); j++) {
                v[j]++;
            }
            v[i + 1] += v[i] - arr[i] + 1;
        }
        // Return steps which is the answer
        return steps;
    }

    // Driver Code
    public static void main(String[] args)
    {
        int arr[] = { 4, 2, 3, 2, 2, 2, 1, 2 };
        int N = arr.length;

        System.out.println(minSteps(arr, N));
    }
}

// This code is contributed by Potta Lokesh
```

### Python 3

```python
# Python program for the above approach

# Function to find minimum steps
# required to reduce all array
# elements to 1
def minSteps(arr, N):

    # Variable to store the answer
    steps = 0

    # Vector with all elements initialized
    # with 0
    v = [0] * (N + 1)

    # Traverse the array
    for i in range(N):

        # Variable to store the numbers of
        # passes that have to add in answer
        # due to element arr[i] after making
        # 0 to (i-1) elements equal to 1
        k = max(0, arr[i] - 1 - v[i])

        # Increment steps by K
        steps += k
        # Update element in v
        v[i] += k

        # Loop to compute how much current element
        # effect the (i+2) to N elements
        for j in range(i + 2, min(i + arr[i], N) + 1):
            v[j] += 1
        v[i + 1] += v[i] - arr[i] + 1

    # Return steps which is the answer
    return steps

# Driver Code
arr = [4, 2, 3, 2, 2, 2, 1, 2]
N = len(arr)

print(minSteps(arr, N))

# This code is contributed by gfgking.
```

### C\#

```csharp
// C# code for the above approach
using System;
class GFG
{

    // Function to find minimum steps
    // required to reduce all array
    // elements to 1
    static int minSteps(int[] arr, int N)
    {

        // Variable to store the answer
        int steps = 0;

        // Vector with all elements initialized
        // with 0
        int[] v = new int[N + 1];

        // Traverse the array
        for (int i = 0; i < N; ++i)
        {

            // Variable to store the numbers of
            // passes that have to add in answer
            // due to element arr[i] after making
            // 0 to (i-1) elements equal to 1
            int k = Math.Max(0, arr[i] - 1 - v[i]);

            // Increment steps by K
            steps += k;

            // Update element in v
            v[i] += k;

            // Loop to compute how much current element
            // effect the (i+2) to N elements
            for (int j = i + 2;
                 j <= Math.Min(i + arr[i], N); j++) {
                v[j]++;
            }
            v[i + 1] += v[i] - arr[i] + 1;
        }

        // Return steps which is the answer
        return steps;
    }

    // Driver Code
    public static void Main()
    {
        int[] arr = { 4, 2, 3, 2, 2, 2, 1, 2 };
        int N = arr.Length;

        Console.Write(minSteps(arr, N));
    }
}

// This code is contributed by gfgking
```

## java 描述语言

```javascript
<script>
    // JavaScript program for the above approach

    // Function to find minimum steps
    // required to reduce all array
    // elements to 1
    const minSteps = (arr, N) => {
        // Variable to store the answer
        let steps = 0;

        // Vector with all elements initialized
        // with 0
        let v = new Array(N + 1).fill(0);

        // Traverse the array
        for (let i = 0; i < N; ++i) {
            // Variable to store the numbers of
            // passes that have to add in answer
            // due to element arr[i] after making
            // 0 to (i-1) elements equal to 1
            let k = Math.max(0, arr[i] - 1 - v[i]);

            // Increment steps by K
            steps += k;
            // Update element in v
            v[i] += k;

            // Loop to compute how much current element
            // effect the (i+2) to N elements
            for (let j = i + 2; j <= Math.min(i + arr[i], N); j++) {
                v[j]++;
            }
            v[i + 1] += v[i] - arr[i] + 1;
        }
        // Return steps which is the answer
        return steps;
    }

    // Driver Code
    let arr = [4, 2, 3, 2, 2, 2, 1, 2];
    let N = arr.length

    document.write(minSteps(arr, N));

    // This code is contributed by rakeshsahni

</script>
```

**Output:**

时间复杂度：O(N<sup>2</sup>)
辅助空间：O(N)