# 计数前缀数组中的最大值小于后缀数组中的最大值的索引

> 原文：[https://www.geeksforgeeks.org/count-indices-where-the-maximum-in-the-prefix-array-is-less-than-that-in-the-suffix-array/](https://www.geeksforgeeks.org/count-indices-where-the-maximum-in-the-prefix-array-is-less-than-that-in-the-suffix-array/)

给定一个大小为 `N` 的数组 `arr[]`，任务是找出最大值小于剩余后缀数组中最大元素的前缀数组的数量。

## 示例

**输入:** `arr[] = {2, 3, 4, 8, 1, 4}`
**输出:** `3`
**解释:**
前缀数组= `{2}`、`{2, 3}`、`{2, 3, 4}`、`{2, 3, 4, 8}`、`{2, 3, 4, 8, 1}`
各自后缀= `{3, 4, 8, 1, 4}`、`{4, 8, 1, 4}`、`{8, 1, 4}`、`{1, 4}`、`{4}`

**输入:** `arr[] = {4, 4, 4, 4, 5}`
**输出:** `4`

## 朴素方法

最简单的方法是找到给定数组的所有可能的前缀和后缀，并计算前缀数组中最大元素小于后缀数组中最大元素的索引数。

**时间复杂度:** `O(N^2)`
**辅助空间:** `O(1)`

## 高效方法

对上述方法进行优化，思路是为数组的每个前缀和后缀存储最大值，然后计算最大值小于其对应后缀数组的前缀数组个数。按照以下步骤解决问题：

*   初始化一个变量，比如说 `ans` 和两个大小为 `N` 的数组 `prefix[]` 和 `suffix[]`。
*   在范围 `[0, N-1]` 内遍历数组 `arr[]`，对于 `prefix[]` 中的每个 `i-th` 索引，将最大元素存储为 `prefix[i] = max(prefix[i-1], arr[i])`。
*   在范围 `[N-1, 0]` 内以相反顺序遍历给定数组，对于 `suffix[]` 中的每个 `i-th` 索引，将最大元素存储为 `suffix[i] = max(suffix[i + 1], arr[i])`。
*   现在，在范围 `[0, N-2]` 内遍历数组 `arr[]`，如果 `prefix[i]` 小于 `suffix[i]`，则以 `1` 递增 `ans`。
*   完成上述步骤后，打印 `ans` 的值作为结果。

下面是上述方法的实现：

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to print the count of indices
// in which the maximum in prefix arrays
// is less than that in the suffix array
void count(int a[], int n)
{
    // If size of array is 1
    if (n == 1) {
        cout << 0;
        return;
    }

    // pre[]: Prefix array
    // suf[]: Suffix array
    int pre[n - 1], suf[n - 1];
    int max = a[0];

    // Stores the required count
    int ans = 0, i;

    pre[0] = a[0];

    // Find the maximum in prefix array
    for (i = 1; i < n - 1; i++) {

        if (a[i] > max)
            max = a[i];

        pre[i] = max;
    }

    max = a[n - 1];
    suf[n - 2] = a[n - 1];

    // Find the maximum in suffix array
    for (i = n - 2; i >= 1; i--) {

        if (a[i] > max)
            max = a[i];

        suf[i - 1] = max;
    }

    // Traverse the array
    for (i = 0; i < n - 1; i++) {

        // If maximum in prefix array
        // is less than maximum in
        // the suffix array
        if (pre[i] < suf[i])
            ans++;
    }

    // Print the answer
    cout << ans;
}

// Driver Code
int main()
{
    int arr[] = { 2, 3, 4, 8, 1, 4 };
    int N = sizeof(arr) / sizeof(arr[0]);

    // Function Call
    count(arr, N);

    return 0;
}
```

### Java

```java
// Java program for the above approach
public class gfg
{
  // Function to print the count of indices
  // in which the maximum in prefix arrays
  // is less than that in the suffix array
  static void count(int a[], int n)
  {

    // If size of array is 1
    if (n == 1)
    {
      System.out.print(0);
      return;
    }

    // pre[]: Prefix array
    // suf[]: Suffix array
    int[] pre = new int[n - 1];
    int[] suf = new int[n - 1];
    int max = a[0];

    // Stores the required count
    int ans = 0, i;
    pre[0] = a[0];

    // Find the maximum in prefix array
    for(i = 1; i < n - 1; i++)
    {
      if (a[i] > max)
        max = a[i];

      pre[i] = max;
    }
    max = a[n - 1];
    suf[n - 2] = a[n - 1];

    // Find the maximum in suffix array
    for(i = n - 2; i >= 1; i--)
    {
      if (a[i] > max)
        max = a[i];
      suf[i - 1] = max;
    }

    // Traverse the array
    for(i = 0; i < n - 1; i++)
    {

      // If maximum in prefix array
      // is less than maximum in
      // the suffix array
      if (pre[i] < suf[i])
        ans++;
    }

    // Print the answer
    System.out.print(ans);
  }

  // Driver code
  public static void main(String[] args)
  {
    int arr[] = { 2, 3, 4, 8, 1, 4 };
    int N = arr.length;

    // Function Call
    count(arr, N);
  }
}

// This code is contributed by divyesh072019.
```

### Python 3

```python
# Python program for the above approach

# Function to print the count of indices
# in which the maximum in prefix arrays
# is less than that in the suffix array
def count(a, n) :

    # If size of array is 1
    if (n == 1) :
        print(0)
        return

    # pre[]: Prefix array
    # suf[]: Suffix array
    pre = [0] * (n - 1)
    suf = [0] * (n - 1)
    max = a[0]

    # Stores the required count
    ans = 0

    pre[0] = a[0]

    # Find the maximum in prefix array
    for i in range(n-1):

        if (a[i] > max):
            max = a[i]

        pre[i] = max

    max = a[n - 1]
    suf[n - 2] = a[n - 1]

    # Find the maximum in suffix array
    for i in range(n-2, 0, -1):

        if (a[i] > max):
            max = a[i]

        suf[i - 1] = max

    # Traverse the array
    for i in range(n - 1):

        # If maximum in prefix array
        # is less than maximum in
        # the suffix array
        if (pre[i] < suf[i]) :
            ans += 1

    # Print the answer
    print(ans)

# Driver Code

arr = [ 2, 3, 4, 8, 1, 4 ]
N = len(arr)

# Function Call
count(arr, N)

# This code is contributed by code_hunt.
```

### C\#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to print the count of indices
// in which the maximum in prefix arrays
// is less than that in the suffix array
static void count(int[] a, int n)
{

    // If size of array is 1
    if (n == 1)
    {
        Console.Write(0);
        return;
    }

    // pre[]: Prefix array
    // suf[]: Suffix array
    int[] pre = new int[n - 1];
    int[] suf = new int[n - 1];
    int max = a[0];

    // Stores the required count
    int ans = 0, i;

    pre[0] = a[0];

    // Find the maximum in prefix array
    for(i = 1; i < n - 1; i++)
    {
        if (a[i] > max)
            max = a[i];

        pre[i] = max;
    }

    max = a[n - 1];
    suf[n - 2] = a[n - 1];

    // Find the maximum in suffix array
    for(i = n - 2; i >= 1; i--)
    {
        if (a[i] > max)
            max = a[i];

        suf[i - 1] = max;
    }

    // Traverse the array
    for(i = 0; i < n - 1; i++)
    {

        // If maximum in prefix array
        // is less than maximum in
        // the suffix array
        if (pre[i] < suf[i])
            ans++;
    }

    // Print the answer
    Console.Write(ans);
}

// Driver code
static void Main()
{
    int[] arr = { 2, 3, 4, 8, 1, 4 };
    int N = arr.Length;

    // Function Call
    count(arr, N);
}
}

// This code is contributed by divyeshrabadiya07
```

## java 描述语言

```
<script>
    // Javascript program for the above approach
    // Function to print the count of indices

    // in which the maximum in prefix arrays
    // is less than that in the suffix array
    function count(a, n)
    {

        // If size of array is 1
        if (n == 1)
        {
            document.write(0);
            return;
        }

        // pre[]: Prefix array
        // suf[]: Suffix array
        let pre = new Array(n - 1);
        let suf = new Array(n - 1);
        let max = a[0];

        // Stores the required count
        let ans = 0, i;

        pre[0] = a[0];

        // Find the maximum in prefix array
        for(i = 1; i < n - 1; i++)
        {
            if (a[i] > max)
                max = a[i];

            pre[i] = max;
        }

        max = a[n - 1];
        suf[n - 2] = a[n - 1];

        // Find the maximum in suffix array
        for(i = n - 2; i >= 1; i--)
        {
            if (a[i] > max)
                max = a[i];

            suf[i - 1] = max;
        }

        // Traverse the array
        for(i = 0; i < n - 1; i++)
        {

            // If maximum in prefix array
            // is less than maximum in
            // the suffix array
            if (pre[i] < suf[i])
                ans++;
        }

        // Print the answer
        document.write(ans);
    }

    let arr = [ 2, 3, 4, 8, 1, 4 ];
    let N = arr.length;

    // Function Call
    count(arr, N);

    // This code is contributed by suresh07.
</script>
```

`Output:`

```

```

`时间复杂度:` `O(N)`
`空间复杂度:` `O(N)`