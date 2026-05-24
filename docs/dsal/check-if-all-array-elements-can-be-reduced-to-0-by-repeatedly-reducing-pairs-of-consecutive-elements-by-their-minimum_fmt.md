# 通过将连续的元素对重复减少其最小值，检查是否所有的数组元素都可以减少到 0

> 原文：[https://www.geeksforgeeks.org/check-if-all-array-elements-can-be-reduced-to-0-by-repeatedly-reducing-pairs-of-consecutive-elements-by-their-minimum/](https://www.geeksforgeeks.org/check-if-all-array-elements-can-be-reduced-to-0-by-repeatedly-reducing-pairs-of-consecutive-elements-by-their-minimum/)

## 问题描述

给定一个由 `N` 个整数组成的数组 `arr[]`，任务是检查是否有可能通过从该对中的两个元素中重复减去任意一对连续数组元素的最小值，将数组元素减少到 `0`。如果可能，则打印 `"是"`。否则，打印 `"否"`。

**示例：**

> **输入：** `arr[] = { 2, 3, 3, 4, 2 }`
> **输出：** 是
> **解释：**
> 可能的方式之一是：
> 选择一对索引 `(0, 1)` 并执行操作，将数组修改为 `arr[] = {0, 1, 3, 4, 2}`。
> 选择一对索引 `(1, 2)`，执行将数组修改为 `arr[] = {0, 0, 2, 4, 2}` 的操作。
> 选择索引对 `(2, 3)`，执行将数组修改为 `arr[] = {0, 0, 0, 2, 2}` 的操作。
> 选择索引对 `(3, 4)`，执行将数组修改为 `arr[] = {0, 0, 0, 0, 0}` 的操作。
> 因此，可以将数组元素转换为零。所以打印 `"是"`

> **输入：** `arr[] = {243, 12, 11}`
> **输出：** 否
> **说明：**
> 不可能把每个数组元素都转换为零。

## 方法

给定的问题可以基于以下观察来解决：

*   假设 `arr[] = {a, b, c, d, e, f}`，那么可以观察到 `a` 应该小于或等于 `b` 即 `a ≤ b` 才能满足上述条件。否则，元素 `a` 将保持大于 `0`。
*   现在将数组修改为 `arr[] = {0, b–a, c, d, e}`，`b–a` 是最左边的元素，因此上面相同的条件也适用于它，即 `b–a ≤ c`。
*   因此可以观察到，在最后重复上述过程之后，偶数索引处的元素之和必须等于奇数索引处的元素之和。

按照以下步骤解决问题：

*   遍历 `[1, N-1]` 范围，检查是否 `arr[i] < arr[i–1]`，然后打印 `"否"` 并中断。否则，将 `arr[i]` 减 `arr[i–1]`。
*   完成上述步骤后，如果上述情况都不满足，则检查 `arr[N–1] = 0` 是否满足。如果发现属实，则打印 `"是"`。否则，打印 `"否"`。
*   使用变量 `i` 在范围 `[0, N–2]` 内遍历给定数组 `arr[]`，并执行以下操作：
    *   如果 `arr[i]` 的值小于 `arr[i + 1]`，则打印 `"否"`，因为所有数组元素都不能减少到 `0`。
    *   否则，将 `arr[i + 1]` 减 `arr[i]`。
*   完成上述步骤后，如果上述情况均不满足，且 `arr[N–1]` 的值为 `0`，则打印 `"是"`。否则，打印 `"否"`。

## 实现

下面是上述方法的实现：

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to check if it is possible
// to convert the array
void checkPossible(int* arr, int n)
{
    // Traverse the array range [1, N-1]
    for (int i = 1; i < n; i++) {

        // If arr[i] < arr[i-1]
        if (arr[i] < arr[i - 1]) {
            cout << "No\n";
            return;
        }

        // Otherwise
        else {

            // Decrement arr[i] by arr[i-1]
            arr[i] -= arr[i - 1];
            arr[i - 1] = 0;
        }
    }

    // If arr[n - 1] is not equal to zero
    if (arr[n - 1] == 0) {
        cout << "Yes\n";
    }

    // Otherwise
    else {
        cout << "No\n";
    }
}

// Driver Code
int main()
{
    int arr[] = { 2, 3, 3, 4, 2 };
    int N = sizeof(arr) / sizeof(arr[0]);

    // Function Call
    checkPossible(arr, N);

    return 0;
}
```

### Java

```java
// Java program to implement
// the above approach
import java.util.*;
class GFG
{

// Function to check if it is possible
// to convert the array
static void checkPossible(int[] arr, int n)
{

    // Traverse the array range [1, N-1]
    for (int i = 1; i < n; i++)
    {

        // If arr[i] < arr[i-1]
        if (arr[i] < arr[i - 1])
        {
            System.out.print("No\n");
            return;
        }

        // Otherwise
        else
        {

            // Decrement arr[i] by arr[i-1]
            arr[i] -= arr[i - 1];
            arr[i - 1] = 0;
        }
    }

    // If arr[n - 1] is not equal to zero
    if (arr[n - 1] == 0)
    {
        System.out.print("Yes\n");
    }

    // Otherwise
    else
    {
        System.out.print("No\n");
    }
}

// Driver Code
public static void main(String args[])
{
    int arr[] = { 2, 3, 3, 4, 2 };
    int N = arr.length;

    // Function Call
    checkPossible(arr, N);
}
}

// This code is contributed by splevel62.
```

### Python

```python
# Python program to implement
# the above approach

# Function to check if it is possible
# to convert the array
def checkPossible(arr, n):

    # Traverse the array range [1, N-1]
    for i in range(1, n):

        # If arr[i] < arr[i-1]
        if (arr[i] < arr[i - 1]):
            print("No");
            return;

        # Otherwise
        else:

            # Decrement arr[i] by arr[i-1]
            arr[i] -= arr[i - 1];
            arr[i - 1] = 0;

    # If arr[n - 1] is not equal to zero
    if (arr[n - 1] == 0):
        print("Yes");

    # Otherwise
    else:
        print("No");

# Driver Code
if __name__ == '__main__':
    arr = [2, 3, 3, 4, 2];
    N = len(arr);

    # Function Call
    checkPossible(arr, N);

# This code is contributed by shikhasingrajput
```

### C#

```csharp
// C# program to implement
// the above approach
using System;
class GFG
{

// Function to check if it is possible
// to convert the array
static void checkPossible(int[] arr, int n)
{

    // Traverse the array range [1, N-1]
    for (int i = 1; i < n; i++)
    {

        // If arr[i] < arr[i-1]
        if (arr[i] < arr[i - 1])
        {
            Console.Write("No\n");
            return;
        }

        // Otherwise
        else
        {

            // Decrement arr[i] by arr[i-1]
            arr[i] -= arr[i - 1];
            arr[i - 1] = 0;
        }
    }

    // If arr[n - 1] is not equal to zero
    if (arr[n - 1] == 0)
    {
        Console.Write("Yes\n");
    }

    // Otherwise
    else
    {
        Console.Write("No\n");
    }
}

// Driver Code
public static void Main()
{
    int[] arr = { 2, 3, 3, 4, 2 };
    int N = arr.Length;

    // Function Call
    checkPossible(arr, N);
}
}

// This code is contributed by susmitakundugoaldanga
```

### JavaScript

```javascript
<script>

// JavaScript program to implement
// the above approach

    // Function to check if it is possible
    // to convert the array
    function checkPossible(arr , n) {

        // Traverse the array range [1, N-1]
        for (i = 1; i < n; i++) {

            // If arr[i] < arr[i-1]
            if (arr[i] < arr[i - 1]) {
                document.write("No\n");
                return;
            }

            // Otherwise
            else {

                // Decrement arr[i] by arr[i-1]
                arr[i] -= arr[i - 1];
                arr[i - 1] = 0;
            }
        }

        // If arr[n - 1] is not equal to zero
        if (arr[n - 1] == 0) {
            document.write("Yes\n");
        }

        // Otherwise
        else {
            document.write("No\n");
        }
    }

    // Driver Code

        var arr = [ 2, 3, 3, 4, 2 ];
        var N = arr.length;

        // Function Call
        checkPossible(arr, N);

// This code contributed by gauravrajsum1

</script>
```

**输出：**

```
Yes
```

## 复杂度分析

*   **时间复杂度：** `O(N)`
*   **辅助空间：** `O(1)`