# 对前 N 个自然数排列中的逆序进行计数

> 原文：[https://www.geeksforgeeks.org/count-inversions-in-a-permutation-of-first-n-natural-numbers/](https://www.geeksforgeeks.org/count-inversions-in-a-permutation-of-first-n-natural-numbers/)

给定一个大小为 `N` 的数组 `arr[]`，表示从 `1` 到 `N` 的数字的排列，任务是计算数组中的反转数。
**注：** 两个数组元素 `a[i]` 和 `a[j]` 如果 `a[i] > a[j]` 和 `i < j` 就形成一个反转。

**示例：**

> **输入：** `arr[] = {2，3，1，5，4}`
> **输出：** `3`
> **说明：** 给定数组有 3 个逆序：`(2，1)`、`(3，1)`、`(5，4)`。
>
> **输入：** `arr[] = {3，1，2}`
> **输出：** `2`
> **说明：** 给定数组有 2 个逆序：`(3，1)`、`(3，2)`。

在下面的文章中已经讨论了解决反转计数的不同方法：

*   [初始和修改合并排序](https://www.geeksforgeeks.org/counting-inversions/)
*   [使用 AVL 树](https://www.geeksforgeeks.org/count-inversions-in-an-array-set-2-using-self-balancing-bst/)
*   [使用 BIT](https://www.geeksforgeeks.org/count-inversions-array-set-3-using-bit/)

**方法：** 这个问题可以用二分搜索法解决。按照以下步骤解决问题：

*   将范围 `[1，N]` 中的数字以递增的顺序存储在向量 `V` 中。
*   初始化一个变量 `ans` 为 `0` 来存储数组 `arr[]` 中的逆序数。
*   使用变量 `i` 在范围 `[0，N-1]` 中迭代。
    *   将向量 `V` 中 `arr[i]` 出现的索引存储在变量 `index` 中。
    *   将向量 `V` 中位置小于 `index` 的数字计数相加，因为它们小于当前元素，因此形成反转。
    *   从向量 `V` 中移除位置 `index` 处的元素。
*   打印 `ans` 的值作为结果。

下面是上述方法的实现：

## C++14

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to count number of inversions in
// a permutation of first N natural numbers
int countInversions(int arr[], int n)
{
    vector<int> v;

    // Store array elements in sorted order
    for (int i = 1; i <= n; i++) {
        v.push_back(i);
    }

    // Store the count of inversions
    int ans = 0;

    // Traverse the array
    for (int i = 0; i < n; i++) {

        // Store the index of first
        // occurrence of arr[i] in vector V
        auto itr = lower_bound(
            v.begin(), v.end(), arr[i]);

        // Add count of smaller elements
        // than current element
        ans += itr - v.begin();

        // Erase current element from
        // vector and go to next index
        v.erase(itr);
    }

    // Print the result
    cout << ans;

    return 0;
}

// Driver Code
int main()
{

    // Given Input
    int arr[] = { 2, 3, 1, 5, 4 };
    int n = sizeof(arr) / sizeof(arr[0]);

    // Function Call
    countInversions(arr, n);

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.util.Vector;

class GFG{

// Function to count number of inversions in
// a permutation of first N natural numbers
static void countInversions(int arr[], int n)
{
    Vector<Integer> v = new Vector<>();

    // Store array elements in sorted order
    for(int i = 1; i <= n; i++)
    {
        v.add(i);
    }

    // Store the count of inversions
    int ans = 0;

    // Traverse the array
    for(int i = 0; i < n; i++)
    {

        // Store the index of first
        // occurrence of arr[i] in vector V
        int itr = v.indexOf(arr[i]);

        // Add count of smaller elements
        // than current element
        ans += itr;

        // Erase current element from
        // vector and go to next index
        v.remove(itr);
    }

    // Print the result
    System.out.println(ans);
}

// Driver code
public static void main(String[] args)
{

    // Given Input
    int arr[] = { 2, 3, 1, 5, 4 };
    int n = arr.length;

    // Function Call
    countInversions(arr, n);
}
}

// This code is contributed by abhinavjain194
```

## Python3

```python
# Python3 program for the above approach
from bisect import bisect_left

# Function to count number of inversions in
# a permutation of first N natural numbers
def countInversions(arr, n):

    v = []

    # Store array elements in sorted order
    for i in range(1, n + 1, 1):
        v.append(i)

    # Store the count of inversions
    ans = 0

    # Traverse the array
    for i in range(n):

        # Store the index of first
        # occurrence of arr[i] in vector V
        itr = bisect_left(v, arr[i])

        # Add count of smaller elements
        # than current element
        ans += itr

        # Erase current element from
        # vector and go to next index
        v = v[:itr] + v[itr + 1 :]

    # Print the result
    print(ans)

# Driver Code
if __name__ == '__main__':

    # Given Input
    arr = [ 2, 3, 1, 5, 4 ]
    n = len(arr)

    # Function Call
    countInversions(arr, n)

# This code is contributed by SURENDRA_GANGWAR
```

## C#

```csharp
// C# program for the above approach
using System;
using System.Collections.Generic;
class GFG {

    // Function to count number of inversions in
    // a permutation of first N natural numbers
    static void countInversions(int[] arr, int n)
    {
        List<int> v = new List<int>();

        // Store array elements in sorted order
        for (int i = 1; i <= n; i++) {
            v.Add(i);
        }

        // Store the count of inversions
        int ans = 0;

        // Traverse the array
        for(int i =0 ;i <n;i ++){

            // Store the index of first
            // occurrence of arr[i] in vector V
            int itr = v.IndexOf(arr[i]);

            // Add count of smaller elements
            // than current element
            ans += itr;

            // Erase current element from
            // vector and go to next index
            v.RemoveAt(itr);
        }

        // Print the result
        Console.WriteLine(ans);
    }

    // Driver code
    public static void Main(string[] args)
    {

        // Given Input
        int[] arr = { 2, 3, 1, 5, 4 };
        int n = arr.Length;

        // Function Call
        countInversions(arr, n);
    }
}

// This code is contributed by ukasp.
```

## JavaScript

```javascript
<script>

// Javascript program for the above approach

// Function to count number of inversions in
// a permutation of first N natural numbers
function countInversions(arr, n)
{
    var v = [];
    var i;

    // Store array elements in sorted order
    for(i = 1; i <= n; i++)
    {
        v.push(i);
    }

    // Store the count of inversions
    var ans = 0;

    // Traverse the array
    for(i = 0; i < n; i++)
    {

        // Store the index of first
        // occurrence of arr[i] in vector V
        var index = v.indexOf(arr[i]);

        // Add count of smaller elements
        // than current element
        ans += index;

        // Erase current element from
        // vector and go to next index
        v.splice(index, 1);
    }

    // Print the result
    document.write(ans);
}

// Driver code

// Given Input
var arr = [ 2, 3, 1, 5, 4 ];
var n = arr.length;

// Function Call
countInversions(arr, n);

// This code is contributed by bgangwar59

</script>
```

**输出：**

```
3
```

**时间复杂度：** `O(N*log(N))`
**辅助空间：** `O(N)`