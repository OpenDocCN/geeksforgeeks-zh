# 检查每个子阵列是否由所有自然数组成，直至其长度

> 原文：[https://www.geeksforgeeks.org/check-for-each-subarray-whether-it-consists-of-all-natural-numbers-up-to-its-length-or-not/](https://www.geeksforgeeks.org/check-for-each-subarray-whether-it-consists-of-all-natural-numbers-up-to-its-length-or-not/)

给定一个表示范围 `[1, N]` 中前 `N` 个自然数的[排列的](https://www.geeksforgeeks.org/array-data-structure/)[数组](https://www.geeksforgeeks.org/array-data-structure/) `arr[]`，对于每个 `i`（1 ≤ i ≤ N），任务是检查是否存在一个长度为 `i` 的子数组，使得它包含范围 `[1, i]` 中的所有数字。
**注：** 使用基于 1 的索引。

**示例：**

> **输入：** `arr[] = {4, 5, 1, 3, 2}`
> **输出：** True False True False True
> **解释：**
> 对于 `i = 1`，子数组 `{arr[2]}` 包含来自 `[1, i]` 且大小为 `i (=1)` 的所有数字。因此，所需的输出为 True。
> 对于 `i = 2`，不存在包含范围 `[1, i]` 中所有数字的大小为 2 的子数组。因此，所需的输出为 False。
> 对于 `i = 3`，子数组 `{arr[2], arr[3], arr[4]}` 包含来自 `[1, i]` 且大小为 `i (=3)` 的所有数字。因此，所需的输出为 True。
> 对于 `i = 4`，不存在包含 `[1, i]` 范围内所有数字的大小为 4 的子数组。因此，所需的输出为 False。
> 对于 `i = 5`，子数组 `{arr[0], arr[1], arr[2], arr[3], arr[4]}` 包含来自 `[1, i]` 且大小为 `i (=5)` 的所有数字。因此，所需的输出为 True。
>
> **输入：** `arr = {1, 4, 3, 2}`
> **输出：** True False False True

## 天真方法

想法是[遍历数组](https://www.geeksforgeeks.org/c-program-to-traverse-an-array/)，对于每个索引，检查是否有一个大小为 `i` 的子数组包含范围 `[1, i]` 内的所有数字。如果发现为真，则打印 `True`。否则，打印 `False`。

**时间复杂度：** O(N²)
**辅助空间：** O(N)

## 高效方法

使用[哈希](https://www.geeksforgeeks.org/hashing-data-structure/)可以高效地存储给定数组中每个元素的位置，从而解决这个问题。按照以下步骤解决问题：

*   创建一个[图](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)，比如说 `map`，来存储给定数组中每个元素的位置。
*   [遍历数组](https://www.geeksforgeeks.org/c-program-to-traverse-an-array/)并将数组中每个元素的位置存储到 `map` 上。
*   创建一个[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)，比如说 `st` 来存储范围 `[1, N]` 中每个元素的索引。
*   初始化两个变量，比如 `Min` 和 `Max`，来存储 `st` 中存在的最小和最大元素。
*   迭代范围 `[1, N]` 并将 `map[i]` 的值插入 `st` 并检查 `Max - Min + 1 == i` 是否存在。如果发现为真，则打印 `True`。
*   否则，打印 `False`。

下面是上述方法的实现：

### C++

```cpp
// C++ program to implement
// the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to check if a subarray of size i exists
// that contain all the numbers in the range [1, i]
void checksubarrayExist1_N(int arr[], int N)
{

    // Store the position
    // of each element of arr[]
    unordered_map<int, int> pos;

    // Traverse the array
    for (int i = 0; i < N; i++) {

        // Insert the position
        // of arr[i]
        pos[arr[i]] = i;
    }

    // Store position of each element
    // from the range [1, N]
    set<int> st;

    // Iterate over the range [1, N]
    for (int i = 1; i <= N; i++) {

        // Insert the index of i into st
        st.insert(pos[i]);
        // Find the smallest element of st
        int Min = *(st.begin());

        // Find the largest element of st
        int Max = *(st.rbegin());

        // If distance between the largest
        // and smallest element of arr[]
        // till i-th index is equal to i
        if (Max - Min + 1 == i) {
            cout << "True ";
        }
        else {
            cout << "False ";
        }
    }
}

// Driver Code
int main()
{
    int arr[] = { 1, 4, 3, 2 };
    int N = sizeof(arr) / sizeof(arr[0]);

    checksubarrayExist1_N(arr, N);
}
```

### Java

```java
// Java program to implement
// the above approach
import java.util.*;

class GFG {

  // Function to check if a subarray of size i exists
  // that contain all the numbers in the range [1, i]
  static void checksubarrayExist1_N(int arr[], int N)
  {

    // Store the position
    // of each element of arr[]
    Map<Integer, Integer> pos=new HashMap<>();

    // Traverse the array
    for (int i = 0; i < N; i++) {

      // Insert the position
      // of arr[i]
      pos.put(arr[i],i);
    }

    // Store position of each element
    // from the range [1, N]
    Set<Integer> st=new HashSet<>();

    // Iterate over the range [1, N]
    for (int i = 1; i <= N; i++) {

      // Insert the index of i into st
      st.add(pos.get(i));
      // Find the smallest element of st
      int Min = Collections.min(st);

      // Find the largest element of st
      int Max = Collections.max(st);

      // If distance between the largest
      // and smallest element of arr[]
      // till i-th index is equal to i
      if (Max - Min + 1 == i) {
        System.out.print("True ");
      }
      else {
        System.out.print("False ");
      }
    }
  }

  // Driver code
  public static void main(String[] args)
  {
    int arr[] = { 1, 4, 3, 2 };
    int N = arr.length;

    checksubarrayExist1_N(arr, N);
  }
}
// This code is contributed by offbeat
```

### Python 3

```python
# Python3 program to implement
# the above approach

# Function to check if a subarray of size i exists
# that contain all the numbers in the range [1, i]
def checksubarrayExist1_N(arr, N):

    # Store the position
    # of each element of arr[]
    pos = {}

    # Traverse the array
    for i in range(N):

        # Insert the position
        # of arr[i]
        pos[arr[i]] = i

    # Store position of each element
    # from the range [1, N]
    st = {}

    # Iterate over the range [1, N]
    for i in range(1, N + 1):

        # Insert the index of i into st
        st[pos[i]] = 1

        # Find the smallest element of st
        Min = sorted(list(st.keys()))[0]

        # Find the largest element of st
        Max = sorted(list(st.keys()))[-1]

        # If distance between the largest
        # and smallest element of arr[]
        # till i-th index is equal to i
        if (Max - Min + 1 == i):
            print("True", end = " ")
        else:
            print("False", end = " ")

# Driver Code
if __name__ == '__main__':
    arr = [1, 4, 3, 2]
    N = len(arr)
    checksubarrayExist1_N(arr, N)

    # This code is contributed by mohit kumar 29.
```

### C#

```csharp
// C# program to implement
// the above approach
using System;
using System.Collections.Generic;
using System.Linq;

class GFG{

// Function to check if a subarray of size i exists
// that contain all the numbers in the range [1, i]
static void checksubarrayExist1_N(int[] arr, int N)
{

    // Store the position
    // of each element of arr[]
    Dictionary<int,
               int> pos = new Dictionary<int,
                                         int>();

    // Traverse the array
    for(int i = 0; i < N; i++)
    {

        // Insert the position
        // of arr[i]
        pos[arr[i]] = i;
    }

    // Store position of each element
    // from the range [1, N]
    HashSet<int> st = new HashSet<int>();

    // Iterate over the range [1, N]
    for(int i = 1; i <= N; i++)
    {

        // Insert the index of i into st
        st.Add(pos[i]);
        // Find the smallest element of st
        int Min = st.Min();

        // Find the largest element of st
        int Max = st.Max();

        // If distance between the largest
        // and smallest element of arr[]
        // till i-th index is equal to i
        if (Max - Min + 1 == i)
        {
            Console.Write("True ");
        }
        else
        {
            Console.Write("False ");
        }
    }
}

// Driver code
public static void Main(string[] args)
{
    int[] arr = { 1, 4, 3, 2 };
    int N = arr.Length;

    checksubarrayExist1_N(arr, N);
}
}

// This code is contributed by ukasp
```

## java 描述语言

```javascript
<script>

// JavaScript program for the above approach

  // Function to check if a subarray of size i exists
  // that contain all the numbers in the range [1, i]
  function checksubarrayExist1_N(arr, N)
  {

    // Store the position
    // of each element of arr[]
    let pos = new Map();

    // Traverse the array
    for (let i = 0; i < N; i++) {

      // Insert the position
      // of arr[i]
      pos.set(arr[i],i);
    }

    // Store position of each element
    // from the range [1, N]
    let st=new Set();

    // Iterate over the range [1, N]
    for (let i = 1; i <= N; i++) {

      // Insert the index of i into st
      st.add(pos.get(i));
      // Find the smallest element of st
      let Min = Math.min(...st);

      // Find the largest element of st
      let Max = Math.max(...st);

      // If distance between the largest
      // and smallest element of arr[]
      // till i-th index is equal to i
      if (Max - Min + 1 == i) {
        document.write("True ");
      }
      else {
        document.write("False ");
      }
    }
  }

// Driver Code

    let arr = [ 1, 4, 3, 2 ];
    let N = arr.length;

    checksubarrayExist1_N(arr, N);

</script>
```

**Output:**

```
True False False True
```

**时间复杂度:** `O(N * log(N))`
**辅助空间:** `O(N)`