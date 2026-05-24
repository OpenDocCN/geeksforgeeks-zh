# 检查是否有可能对 N 个对象进行着色，以便对每个对象使用完全不同的颜色

> 原文: [https://www.geeksforgeeks.org/check-if-it-is-possible-to-color-n-objects-such-that-for-ith-object-exactly-arri-distinct-colors-are-used/](https://www.geeksforgeeks.org/check-if-it-is-possible-to-color-n-objects-such-that-for-ith-object-exactly-arri-distinct-colors-are-used/)

给定由 `N` 个正整数组成的数组 `arr[]`，任务是检查是否有可能对 `N` 个对象进行着色，使得对于数组中的第 `i` 个元素，除了第 `i` 个对象之外，在对所有对象进行着色时，精确地存在 `arr[i]` 种不同的颜色。

**示例:**

> **输入:** `arr[] = {1, 2, 2}`
> **输出:** 是
> **解释:**
> 可能的配色方式之一是: {“红”, “蓝”, “蓝”}。
> 1. 对于 `arr[0]` (=1)，正好有一种不同的颜色，即“蓝色”。
> 2. 对于 `arr[1]` (=2)，正好有两种不同的颜色，即“蓝色”和“红色”。
> 3. 对于 `arr[2]` (=2)，正好有两种不同的颜色，即“蓝色”和“红色”。
>
> **输入:** `arr[] = {4, 3, 4, 3, 4}`
> **输出:** 否

## 方法

根据以下观察结果可以解决问题:

1. 对于 `2` 个对象，在计算不同颜色的数量时，通常会考虑 `n-2` 个对象。因此，数组 `arr[]` 的最大元素和最小元素之间最多只能有 `1` 的差值。
2. 现在有两种情况:
    1. 如果最大元素和最小元素相等，那么只有当该元素等于 `n-1` 或该元素小于等于 `n/2` 时，答案才是“是”，因为每种颜色可以被多次使用。
    2. 如果最大元素和最小元素之间的差值为 `1`，那么 `n` 个对象中不同颜色的数量必须等于最大元素，因为最小元素比最大元素小 `1`。
        * 现在假设最小元素的频率是 `x`，最大元素的频率是 `y`，那么当且仅当 `x+1 ≤ a ≤ x+y/2`（基于观察）时，答案才是“是”。

按照以下步骤解决问题:

* 首先对数组进行升序排序。
* 如果 `arr[N-1]` 和 `arr[0]` 的差值大于 `1`，则打印“否”。
* 否则，如果 `arr[N-1]` 等于 `arr[0]`，则检查以下内容:
    * 如果 `arr[N-1] = N-1` 或 `2*arr[N-1] <= N`，则打印“是”。
    * 否则，打印“否”。
* 否则，计算最小和最大元素的频率并将其存储在变量中，比如 `X` 和 `Y`，然后执行以下操作:
    * 如果 `arr[N-1]` 大于等于 `X+1` 且 `arr[N-1]` 小于等于 `X+Y/2`，则打印“是”。
    * 否则，打印“否”。

## 以下是上述方法的实现

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to check if coloring is
// possible with give conditions
string checkValid(int arr[], int N)
{
    // Sort the vector
    sort(arr, arr + N);

    // Coloring not possible in case of
    // maximum - minimum element > 1
    if (arr[N - 1] - arr[0] > 1)
        return "No";

    // case 1
    else if (arr[N - 1] == arr[0]) {

        // If h is equal to N-1 or
        // N is greater than 2*h
        if (arr[N - 1] == N - 1
            || 2 * arr[N - 1] <= N)
            return "Yes";
        else
            return "No";
    }
    // Case 2
    else {
        // Stores frequency of minimum element
        int x = 0;

        for (int i = 0; i < N; i++) {

            // Frequency  of minimum element
            if (arr[i] == arr[0])
                x++;
        }

        // Stores frequency of maximum element
        int y = N - x;

        // Condition for case 2
        if ((arr[N - 1] >= x + 1)
            and (arr[N - 1] <= x + y / 2))
            return "Yes";
        else
            return "No";
    }
}

// Driver Code
int main()
{
    // GivenInput
    int arr[] = { 1, 2, 2 };
    int N = sizeof(arr) / sizeof(arr[0]);

    // Function Call
    cout << checkValid(arr, N);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.util.*;

class GFG{

// Function to check if coloring is
// possible with give conditions
static String checkValid(int arr[], int N)
{
    // Sort the vector
    Arrays.sort(arr);

    // Coloring not possible in case of
    // maximum - minimum element > 1
    if (arr[N - 1] - arr[0] > 1)
        return "No";

    // Case 1
    else if (arr[N - 1] == arr[0])
    {
        // If h is equal to N-1 or
        // N is greater than 2*h
        if (arr[N - 1] == N - 1
            || 2 * arr[N - 1] <= N)
            return "Yes";
        else
            return "No";
    }

    // Case 2
    else
    {
        // Stores frequency of minimum element
        int x = 0;

        for(int i = 0; i < N; i++)
        {
            // Frequency  of minimum element
            if (arr[i] == arr[0])
                x++;
        }

        // Stores frequency of maximum element
        int y = N - x;

        // Condition for case 2
        if ((arr[N - 1] >= x + 1) &&
            (arr[N - 1] <= x + y / 2))
            return "Yes";
        else
            return "No";
    }
}

// Driver Code
public static void main(String[] args)
{
    // Given Input
    int[] arr = { 1, 2, 2 };
    int N = arr.length;

    // Function Call
    System.out.print(checkValid(arr, N));
}
}

// This code is contributed by sanjoy_62
```

### Python 3

```python
# Python3 program for the above approach

# Function to check if coloring is
# possible with give conditions
def checkValid(arr, N):
    # Sort the vector
    arr = sorted(arr)

    # Coloring not possible in case of
    # maximum - minimum element > 1
    if (arr[N - 1] - arr[0] > 1):
        return "No"

    # case 1
    elif (arr[N - 1] == arr[0]):
        # If h is equal to N-1 or
        # N is greater than 2*h
        if (arr[N - 1] == N - 1 or
        2 * arr[N - 1] <= N):
            return "Yes"
        else:
            return "No"
    # Case 2
    else:
        # Stores frequency of minimum element
        x = 0

        for i in range(N):
            # Frequency of minimum element
            if (arr[i] == arr[0]):
                x += 1

        # Stores frequency of maximum element
        y = N - x

        # Condition for case 2
        if ((arr[N - 1] >= x + 1) and
            (arr[N - 1] <= x + y // 2)):
            return "Yes"
        else:
            return "No"

# Driver Code
if __name__ == '__main__':
    # Given Input
    arr = [ 1, 2, 2 ]
    N = len(arr)

    # Function Call
    print (checkValid(arr, N))

# This code is contributed by mohit kumar 29
```

### C#

```csharp
// C# program for the above approach
using System;
using System.Collections.Generic;

class GFG{

// Function to check if coloring is
// possible with give conditions
static string checkValid(int []arr, int N)
{
    // Sort the vector
    Array.Sort(arr);

    // Coloring not possible in case of
    // maximum - minimum element > 1
    if (arr[N - 1] - arr[0] > 1)
        return "No";

    // case 1
    else if (arr[N - 1] == arr[0]) {
        // If h is equal to N-1 or
        // N is greater than 2*h
        if (arr[N - 1] == N - 1
            || 2 * arr[N - 1] <= N)
            return "Yes";
        else
            return "No";
    }
    // Case 2
    else {
        // Stores frequency of minimum element
        int x = 0;

        for (int i = 0; i < N; i++) {
            // Frequency  of minimum element
            if (arr[i] == arr[0])
                x++;
        }

        // Stores frequency of maximum element
        int y = N - x;

        // Condition for case 2
        if ((arr[N - 1] >= x + 1)
            && (arr[N - 1] <= x + y / 2))
            return "Yes";
        else
            return "No";
    }
}

// Driver Code
public static void Main()
{
    // GivenInput
    int []arr = { 1, 2, 2 };
    int N = arr.Length;

    // Function Call
    Console.Write(checkValid(arr, N));
}
}

// This code is contributed by SURENDRA_GANGWAR.
```

## java 描述语言

```javascript
<script>

// Javascript program for the above approach

// Function to check if coloring is
// possible with give conditions
function checkValid(arr, N)
{

    // Sort the vector
    arr.sort((a, b) => a - b);

    // Coloring not possible in case of
    // maximum - minimum element > 1
    if (arr[N - 1] - arr[0] > 1)
        return "No";

    // Case 1
    else if (arr[N - 1] == arr[0])
    {

        // If h is equal to N-1 or
        // N is greater than 2*h
        if (arr[N - 1] == N - 1 ||
        2 * arr[N - 1] <= N)
            return "Yes";
        else
            return "No";
    }

    // Case 2
    else
    {

        // Stores frequency of minimum element
        let x = 0;

        for(let i = 0; i < N; i++)
        {

            // Frequency  of minimum element
            if (arr[i] == arr[0])
                x++;
        }

        // Stores frequency of maximum element
        let y = N - x;

        // Condition for case 2
        if ((arr[N - 1] >= x + 1) &&
            (arr[N - 1] <= x + y / 2))
            return "Yes";
        else
            return "No";
    }
}

// Driver Code

// GivenInput
let arr = [ 1, 2, 2 ];
let N = arr.length;

// Function Call
document.write(checkValid(arr, N));

// This code is contributed by gfgking

</script>
```

`Output`

```
Yes
```

`时间复杂度:` O(N*log(N))
`辅助空间:` O(1)