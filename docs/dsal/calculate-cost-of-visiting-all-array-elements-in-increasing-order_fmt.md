# 按递增顺序计算访问所有数组元素的成本

> 原文：[https://www.geeksforgeeks.org/calculate-cost-of-visiting-all-array-elements-in-increasing-order/](https://www.geeksforgeeks.org/calculate-cost-of-visiting-all-array-elements-in-increasing-order/)

如果从索引 `i` 到索引 `j` 的移动成本是 `i` 和 `j` 之间的绝对差值，那么给定一个由 `N` 个整数组成的数组 `arr[]`，任务是从 `0` 开始，以升序查找访问所有数组元素的总成本。

## 示例

> **输入:** `arr[] = { 4, 3, 2, 5, 1 }`
> **输出:** `11`
> **解释:**
> 从索引 `0` 跳转到索引 `4`。成本 = `abs(4 - 0) = 4`。
> 从索引 `4` 跳到索引 `2`。成本 = `abs(4 - 2) = 2`。
> 从索引 `2` 跳转到索引 `1`。成本 = `abs(2 - 1) = 1`。
> 从索引 `1` 跳到索引 `0`。成本 = `abs(1 - 0) = 1`。
> 从索引 `0` 跳到索引 `3`。成本 = `abs(0 - 3) = 3`。
> 因此，按升序访问所有数组元素的总开销 = `(4 + 2 + 1 + 1 + 3) = 11`。
>
> **输入:** `arr[] = { 1, 2, 3 }`
> **输出:** `2`

## 方法

思路是利用对向量对进行排序的概念。按照以下步骤解决问题：

*   初始化一个 `vector<pair<int, int>>`，比如 `v`，来存储元素对及其各自的位置。
*   遍历数组 `arr[]` 并在向量 `v` 中推入对 `{arr[i], i}`。
*   初始化两个变量，比如 `ans = 0` 和 `last = 0`，来存储所需的总成本和上次访问元素的索引。
*   按升序对向量对进行排序。
*   遍历向量 `v` 并将 `ans` 增加 `abs(v[i].second - last)`。将 `last` 更新为 `last = v[i].second`。
*   完成上述步骤后，将获得的答案打印为 `ans`。

下面是上述方法的实现：

## C++

```cpp
// C++ implementation of the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to calculate total
// cost of visiting array
// elements in increasing order
int calculateDistance(int arr[], int N)
{
    // Stores the pair of element
    // and their positions
    vector<pair<int, int> > v;

    // Traverse the array arr[]
    for (int i = 0; i < N; i++)

        // Push the pair {arr[i], i} in v
        v.push_back({ arr[i], i });

    // Sort the vector in ascending order.
    sort(v.begin(), v.end());

    // Stores the total cost
    int ans = 0;

    // Stores the index of last element visited
    int last = 0;

    // Traverse the vector v
    for (auto j : v) {

        // Increment ans
        ans += abs(j.second - last);

        // Assign
        last = j.second;
    }

    // Return ans
    return ans;
}

// Driver Code
int main()
{
    int arr[] = { 4, 3, 2, 5, 1 };
    int N = sizeof(arr) / sizeof(arr[0]);
    cout << calculateDistance(arr, N);
}
```

## Java

```java
// java program for the above approach
import java.io.*;
import java.lang.*;
import java.util.*;

class GFG {

  // Pair class
  static class Pair {

    int first;
    int second;

    Pair(int first, int second)
    {
      this.first = first;
      this.second = second;
    }
  }

  // Function to calculate total
  // cost of visiting array
  // elements in increasing order
  static int calculateDistance(int arr[], int N)
  {
    // Stores the pair of element
    // and their positions
    Pair v[] = new Pair[N];

    // Traverse the array arr[]
    for (int i = 0; i < N; i++)

      // Push the pair {arr[i], i} in v
      v[i] = new Pair(arr[i], i);

    // Sort the vector in ascending order.
    Arrays.sort(v, (p1, p2) -> {
      if (p1.first != p2.first)
        return p1.first - p2.first;
      return p1.second - p2.second;
    });

    // Stores the total cost
    int ans = 0;

    // Stores the index of last element visited
    int last = 0;

    // Traverse the vector v
    for (Pair j : v) {

      // Increment ans
      ans += Math.abs(j.second - last);

      // Assign
      last = j.second;
    }

    // Return ans
    return ans;
  }

  // Driver Code
  public static void main(String[] args)
  {
    int arr[] = { 4, 3, 2, 5, 1 };
    int N = arr.length;

    // Function call
    System.out.println(calculateDistance(arr, N));
  }
}

// This code is contributed by Kingash.
```

## Python 3

```python
# Python3 implementation of the above approach

# Function to calculate total
# cost of visiting array
# elements in increasing order
def calculateDistance(arr, N):

    # Stores the pair of element
    # and their positions
    v = []

    # Traverse the array arr[]
    for i in range(N):

        # Push the pair {arr[i], i} in v
        v.append([arr[i], i])

    # Sort the vector in ascending order.
    v.sort()

    # Stores the total cost
    ans = 0

    # Stores the index of last element visited
    last = 0

    # Traverse the vector v
    for j in v:

        # Increment ans
        ans += abs(j[1] - last)

        # Assign
        last = j[1]

    # Return ans
    return ans

# Driver Code
if __name__ == "__main__" :

    arr = [ 4, 3, 2, 5, 1 ]
    N = len(arr)

    print(calculateDistance(arr, N))

# This code is contributed by AnkThon
```

## JavaScript

```javascript
<script>
// Javascript implementation of the above approach

// Function to calculate total
// cost of visiting array
// elements in increasing order
function calculateDistance(arr, N)
{
    // Stores the pair of element
    // and their positions
    var v = [];

    // Traverse the array arr[]
    for (var i = 0; i < N; i++)
    {
        // Push the pair {arr[i], i} in v
        v.push([ arr[i], i ]);
    }

    // Sort the vector in ascending order.
    v = v.sort();

    // Stores the total cost
    var ans = 0;

    // Stores the index of last element visited
    var last = 0;

    // Traverse the vector v
    for (var i = 0; i < N; i++)
    {
        // Increment ans
        ans += Math.abs(v[i][1] - last);

        // Assign
        last = v[i][1];
    }

    // Return ans
    return ans;
}

// Driver Code
var arr = [ 4, 3, 2, 5, 1 ];
var N = arr.length;
document.write(calculateDistance(arr, N));

// This code is contributed by Shubhamsingh10
</script>
```

**输出:**

```
11
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(N)`