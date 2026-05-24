# 检查一个数组是否可以分成由单个不同元素组成的长度为 M 的 K 个连续的非重叠子数组

> 原文: [https://www.geeksforgeeks.org/check-if-an-array-can-be-split-into-k-consecutive-non-overlapping-subarrays-of-length-m/](https://www.geeksforgeeks.org/check-if-an-array-can-be-split-into-k-consecutive-non-overlapping-subarrays-of-length-m/)

给定两个整数 `M` 和 `K` 以及一个由 `N` 个正整数组成的数组 `arr[]`，任务是检查该数组是否可以拆分为长度为 `M` 的 `K` 个连续的不重叠的子数组，使得每个子数组由一个单独的不同元素组成。如果发现是真的，则打印 `"是"`。否则，打印 `"否"`。

## 示例

> **输入:** `arr[] = {6，1，3，3，3，3}`，`M = 1`，`K = 3`
> **输出:** 是
> **说明:**
> `K` 个连续的不重叠子阵为 `{6}`、`{1}`、`{3，3，3，3}`。

> **输入:** `arr[] = {3，5，3，5，3，1}`，`M = 2`，`K = 3`
> **输出:** 否

## 方法

通过使用简单的数组遍历并检查当前索引 `i` 处的元素和索引 `(i + M)` 处的元素是否相同，可以解决给定的问题。按照以下步骤解决问题:

*   初始化两个变量，分别用 `1` 和 `0` 计数 `count` 和 `t`，分别存储模式匹配的总计数和模式匹配的当前长度。
*   使用变量 `i` 在范围 `[0，N–M–1]` 内遍历给定数组，并执行以下操作:
    *   如果 `arr[i]` 和 `arr[i + M]` 的值相同，那么将 `t` 增加 `1`，如果 `t` 与 `m` 相同，那么将 `t` 更新为 `0`，并增加 `count`。如果 `count` 的值为 `K`，则打印 `"是"` 并跳出循环。
    *   否则，如果 `t` 是 `M`，那么将 `count` 增加 `1`。
*   经过上述步骤后，如果 `count` 的值与 `K` 不相同，则打印 `"否"`，因为不存在这样的模式。

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to check if array can be split
// into K consecutive and non-overlapping
// subarrays of length M consisting of a
// single distinct element
string checkPattern(int arr[], int m,
                    int k, int n)
{
    int count = 1, t = 0;

    // Traverse over the range [0, N - M - 1]
    for (int i = 0; i < n - m; i++) {

        // Check if arr[i] is the
        // same as arr[i + m]
        if (arr[i] == arr[i + m]) {

            // Increment current length
            // t of pattern matched by 1
            t++;

            // Check if t is equal to m,
            // increment count of total
            // repeated pattern
            if (t == m) {

                t = 0;
                count++;

                // Return true if length of
                // total repeated pattern is k
                if (count == k) {
                    return "Yes";
                }
            }
        }

        else {

            // Update length of the
            // current pattern
            t = 0;

            // Update count to 1
            count = 1;
        }
    }

    // Finally return false if
    // no pattern found
    return "No";
}

// Driver Code
int main()
{
    int arr[] = { 6, 1, 3, 3, 3, 3 };
    int M = 1, K = 3;
    int N = sizeof(arr) / sizeof(arr[0]);

    cout << checkPattern(arr, M, K, N);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.util.*;
class GFG
{

// Function to check if array can be split
// into K consecutive and non-overlapping
// subarrays of length M consisting of a
// single distinct element
static String checkPattern(int arr[], int m,
                    int k, int n)
{
    int count = 1, t = 0;

    // Traverse over the range [0, N - M - 1]
    for (int i = 0; i < n - m; i++)
    {

        // Check if arr[i] is the
        // same as arr[i + m]
        if (arr[i] == arr[i + m])
        {

            // Increment current length
            // t of pattern matched by 1
            t++;

            // Check if t is equal to m,
            // increment count of total
            // repeated pattern
            if (t == m)
            {
                t = 0;
                count++;

                // Return true if length of
                // total repeated pattern is k
                if (count == k)
                {
                    return "Yes";
                }
            }
        }
        else
        {

            // Update length of the
            // current pattern
            t = 0;

            // Update count to 1
            count = 1;
        }
    }

    // Finally return false if
    // no pattern found
    return "No";
}

// Driver Code
public static void main(String[] args)
{
    int arr[] = { 6, 1, 3, 3, 3, 3 };
    int M = 1, K = 3;
    int N = arr.length;
    System.out.print(checkPattern(arr, M, K, N));
}
}

// This code is contributed by 29AjayKumar
```

### Python 3

```python
# Python 3 program for the above approach

# Function to check if array can be split
# into K consecutive and non-overlapping
# subarrays of length M consisting of a
# single distinct element
def checkPattern(arr, m, k, n):
    count = 1
    t = 0

    # Traverse over the range [0, N - M - 1]
    for i in range(n - m):

        # Check if arr[i] is the
        # same as arr[i + m]
        if (arr[i] == arr[i + m]):

            # Increment current length
            # t of pattern matched by 1
            t += 1

            # Check if t is equal to m,
            # increment count of total
            # repeated pattern
            if (t == m):
                t = 0
                count += 1

                # Return true if length of
                # total repeated pattern is k
                if (count == k):
                    return "Yes"

        else:
            # Update length of the
            # current pattern
            t = 0

            # Update count to 1
            count = 1

    # Finally return false if
    # no pattern found
    return "No"

# Driver Code
if __name__ == '__main__':
    arr  =  [6, 1, 3, 3, 3, 3]
    M = 1
    K = 3
    N = len(arr)

    print(checkPattern(arr, M, K, N))

    # This code is contributed by bgangwar59.
```

### C\#

```csharp
// C# program for the above approach
using System;

public class GFG
{

  // Function to check if array can be split
  // into K consecutive and non-overlapping
  // subarrays of length M consisting of a
  // single distinct element
  static String checkPattern(int []arr, int m,
                             int k, int n)
  {
    int count = 1, t = 0;

    // Traverse over the range [0, N - M - 1]
    for (int i = 0; i < n - m; i++)
    {

      // Check if arr[i] is the
      // same as arr[i + m]
      if (arr[i] == arr[i + m])
      {

        // Increment current length
        // t of pattern matched by 1
        t++;

        // Check if t is equal to m,
        // increment count of total
        // repeated pattern
        if (t == m)
        {
          t = 0;
          count++;

          // Return true if length of
          // total repeated pattern is k
          if (count == k)
          {
            return "Yes";
          }
        }
      }
      else
      {

        // Update length of the
        // current pattern
        t = 0;

        // Update count to 1
        count = 1;
      }
    }

    // Finally return false if
    // no pattern found
    return "No";
  }

  // Driver Code
  public static void Main(String[] args)
  {
    int []arr = { 6, 1, 3, 3, 3, 3 };
    int M = 1, K = 3;
    int N = arr.Length;
    Console.Write(checkPattern(arr, M, K, N));
  }
}

// This code is contributed by Rajput-Ji
```

# JavaScript 模式检查示例

```javascript
<script>

// Js program for the above approach

// Function to check if array can be split
// into K consecutive and non-overlapping
// subarrays of length M consisting of a
// single distinct element
function checkPattern( arr, m, k, n)
{
    let count = 1, t = 0;

    // Traverse over the range [0, N - M - 1]
    for (let i = 0; i < n - m; i++) {

        // Check if arr[i] is the
        // same as arr[i + m]
        if (arr[i] == arr[i + m]) {

            // Increment current length
            // t of pattern matched by 1
            t++;

            // Check if t is equal to m,
            // increment count of total
            // repeated pattern
            if (t == m) {

                t = 0;
                count++;

                // Return true if length of
                // total repeated pattern is k
                if (count == k) {
                    return "Yes";
                }
            }
        }

        else {

            // Update length of the
            // current pattern
            t = 0;

            // Update count to 1
            count = 1;
        }
    }

    // Finally return false if
    // no pattern found
    return "No";
}

// Driver Code
let arr = [ 6, 1, 3, 3, 3, 3 ];
let M = 1, K = 3;
let N = arr.length;
document.write( checkPattern(arr, M, K, N));
</script>
```

**输出：**

```
Yes
```

**时间复杂度：** `O(N)`
**辅助空间：** `O(1)`