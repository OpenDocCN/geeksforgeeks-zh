# 使用二分搜索法算法重新排列数组找到 K，无需排序

> 原文：[https://www.geeksforgeeks.org/rearrange-array-to-find-k-using-binary-search-algorithm-without-sorting/](https://www.geeksforgeeks.org/rearrange-array-to-find-k-using-binary-search-algorithm-without-sorting/)

给定一个由 `N` 个不同整数组成的[数组](https://www.geeksforgeeks.org/array-data-structure/)、 `arr[]` 和一个整数 `K`，任务是[重新排列给定的数组](https://www.geeksforgeeks.org/tag/array-rearrange/)，使得 `K` 可以在重新排列的数组中借助[二分搜索法算法](https://www.geeksforgeeks.org/binary-search/)找到。请注意，数组不会被排序。

**示例：**

> **输入**：`arr[] = {10, 7, 2, 5, 3, 8}`，`K = 7`
> **输出**：`3 7 8 5 2 10`
> **解释**：使用二分搜索法在输出数组 `{3, 7, 8, 5, 2, 10}` 中查找 `K`：
> - 最初，左(`L`) = 0，右(`R`) = 5，`mid = 2`，即 8（不等于 `K`）
> - 由于 8 > `K`，因此 `R = 1`，`mid = 3`（不等于 `K`）
> - 由于 3 < `K`，因此左(`L`) = 1，右(`R`) = 1，`mid = 1`，即 7（等于 `K`）
> 因此使用二分搜索法可以在输出数组中找到 `K`，即使数组没有排序。

> **输入**：`arr[] = {10, 7, 2, 5, 8, 6}`，`K = 6`
> **输出**：`8 7 5 10 2 6`

**方法**：给定的问题可以基于以下观察来解决：

1.  整数 `k` 可以通过[二分搜索法](https://www.geeksforgeeks.org/binary-search/)在排序数组 `arr[]` 中找到，如下所示：
    1.  首先，`l = 0` 且 `r = n-1`。
    2.  当 `l` 小于或等于 `r` 时：
        1.  找到当前区间 `[l, r]` 的中点作为 `mid = (l+r)/2`。
        2.  如果 `arr[mid]` 等于 `k`，则返回 `true`。
        3.  否则，如果 `arr[mid]` 大于 `k`，则将 `r` 更新为 `mid-1`，即跳过 `mid` 右侧的所有元素。
        4.  否则，如果 `arr[mid]` 小于 `k`，则将 `l` 更新为 `mid+1`，即跳过 `mid` 剩余的所有元素。
    3.  如果找不到 `k`，则返回 `false`。
2.  二分搜索法在无序数组上可能会失败，因为数组不满足单调递增或递减的条件。然而，有时二分搜索法也可能适用于无序数组。
3.  例如，假设给定数组 `arr[]` 等于 `{2, 1, 5, 4, 3}`，且 `k` 等于 `2`。那么算法工作如下：
    1.  在第一次迭代中：
        *   `l = 0` 且 `r = 4`，所以 `mid = (4+0)/2 = 2`。
        *   `arr[2]`（= 5）大于 `2`，因此将 `1` 赋给 `r`。现在 `r` 变为 `1`。
    2.  在第二次迭代中：
        *   `l = 0` 且 `r = 1`，所以 `mid = (1+0)/2 = 0`。
        *   `arr[0]`（= 2）等于 `2`。因此，返回 `true`。
4.  因此，从以上可以观察到，从中间位置开始取索引 `x` 有两种情况：
    1.  如果 `middle` 小于 `x`，那么 `arr[middle]` 必须小于 `arr[x]` 才能向 `middle` 的右侧移动。
    2.  否则，如果 `middle` 大于 `x`，那么 `arr[middle]` 必须大于 `arr[x]` 才能向 `middle` 的左侧移动。

按照以下步骤解决问题：

*   初始化一个[数组](https://www.geeksforgeeks.org/introduction-to-arrays/)，比如 `ans[]`，所有数组元素为 `-1`，用于存储重新排列的数组。
*   另外，初始化两个[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)，表示 `smaller` 和 `greater`，来存储小于和大于 `K` 的元素。
*   [遍历数组](https://www.geeksforgeeks.org/c-program-to-traverse-an-array/) `arr[]`，如果当前元素小于 `K`，则将其推入 `smaller` 中。否则，如果大于 `K`，则推入 `greater`。
*   在数组 `arr[]` 中找到元素 `K` 的索引，然后将其值赋给 `K`。
*   初始化两个变量，比如 `low` 为 `0` 和 `high` 为 `N-1`，执行二分搜索。
*   重复直到 `low` 小于或等于 `high`，并执行以下步骤：
    *   找到当前范围 `[low, high]` 的中间值，并将其存储在一个变量中，比如 `mid`。
    *   如果 `mid` 小于 `K`，则执行以下操作：
        *   如果 `smaller.size()` 为 `0`，则打印 `-1` 并返回。
        *   否则，将向量 `smaller` 的[最后一个元素](https://www.geeksforgeeks.org/last-element-of-vector-in-cpp-accessing-and-updating/)分配给 `ans[mid]`，然后[弹出 `smaller` 的最后一个元素](https://www.geeksforgeeks.org/vectorpush_back-vectorpop_back-c-stl/)。
    *   如果 `mid` 大于 `K`，则执行以下操作：
        *   如果 `greater.size()` 为 `0`，则打印 `-1` 并返回。
        *   否则，将向量 `greater` 的[最后一个元素](https://www.geeksforgeeks.org/last-element-of-vector-in-cpp-accessing-and-updating/)分配给 `ans[mid]`，然后[弹出 `greater` 的最后一个元素](https://www.geeksforgeeks.org/vectorpush_back-vectorpop_back-c-stl/)。
    *   如果 `mid` 等于 `K`，则将 `arr[K]` 分配给 `ans[mid]`，然后[中断](https://www.geeksforgeeks.org/break-statement-cc/)循环。
*   完成上述步骤后，[遍历数组](https://www.geeksforgeeks.org/c-program-to-traverse-an-array/) `ans[]`，如果当前元素为 `-1`（即未填充），则为其分配任何未使用的元素。
*   最后，[打印数组](https://www.geeksforgeeks.org/c-program-to-print-an-array-using-recursion/) `ans[]` 作为重新排列的数组。

下面是上述方法的实现：

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to rearrange the array
void Rearrange(int arr[], int K, int N)
{
    // Stores the rearranged array
    int ans[N + 1];

    // Stores whether the arrangement
    // is possible or not
    int f = -1;

    for (int i = 0; i < N; i++) {
        ans[i] = -1;
    }

    // Update K with the position of K
    K = find(arr, arr + N, K) - arr;

    // Stores all elements lesser than
    // and greater than in vector smaller
    // and greater respectively
    vector<int> smaller, greater;

    // Traverse the array arr[]
    for (int i = 0; i < N; i++) {

        // If arr[i] is less than arr[K]
        if (arr[i] < arr[K])
            smaller.push_back(arr[i]);

        // Else
        else if (arr[i] > arr[K])
            greater.push_back(arr[i]);
    }

    int low = 0, high = N - 1;

    // Iterate unil low is less than or
    // equal to high
    while (low <= high) {

        // Stores mid point
        int mid = (low + high) / 2;

        // If mid is equal to K
        if (mid == K) {
            ans[mid] = arr[K];
            f = 1;
            break;
        }

        // If mid is less than K
        else if (mid < K) {
            if (smaller.size() == 0) {
                break;
            }
            ans[mid] = smaller.back();
            smaller.pop_back();
            low = mid + 1;
        }
        // If mid is greater than K
        else {
            if (greater.size() == 0) {
                break;
            }
            ans[mid] = greater.back();
            greater.pop_back();
            high = mid - 1;
        }
    }

    // If f is -1
    if (f == -1) {
        cout << -1 << endl;
        return;
    }

    // Iterate in the range [1, N]
    for (int i = 0; i < N; i++) {

        // If ans[i] is equal to -1
        if (ans[i] == -1) {

            if (smaller.size()) {
                ans[i] = smaller.back();
                smaller.pop_back();
            }
            else if (greater.size()) {
                ans[i] = greater.back();
                greater.pop_back();
            }
        }
    }

    // Print the rearranged array
    for (int i = 0; i < N; i++)
        cout << ans[i] << " ";
    cout << endl;
}

// Driver Code
int main()
{
    // Input
    int arr[] = { 10, 7, 2, 5, 3, 8 };
    int K = 7;
    int N = sizeof(arr) / sizeof(arr[0]);

    // Function Call
    Rearrange(arr, K, N);

    return 0;
}
```

## Java 语言

```java
// Java program for the above approach

import java.util.*;
public class GFG
{

// Function to rearrange the array
static void Rearrange(int arr[], int K, int N)
{

    // Stores the rearranged array
    int ans[] = new int[N + 1];

    // Stores whether the arrangement
    // is possible or not
    int f = -1;

    for (int i = 0; i < N; i++) {
        ans[i] = -1;
    }

    // Update K with the position of K
   for (int i = 0; i < arr.length; i++)
   {
       if (arr[i] == K)
       {
           K = i;
           break;
       }
   }

    // Stores all elements lesser than
    // and greater than in vector smaller
    // and greater respectively
     Vector<Integer> smaller = new Vector<Integer>();
     Vector<Integer> greater = new Vector<Integer>();

    // Traverse the array arr[]
    for (int i = 0; i < N; i++) {

        // If arr[i] is less than arr[K]
        if (arr[i] < arr[K])
            smaller.add(arr[i]);

        // Else
        else if (arr[i] > arr[K])
            greater.add(arr[i]);
    }

    int low = 0, high = N - 1;

    // Iterate unil low is less than or
    // equal to high
    while (low <= high) {

        // Stores mid point
        int mid = (low + high) / 2;

        // If mid is equal to K
        if (mid == K) {
            ans[mid] = arr[K];
            f = 1;
            break;
        }

        // If mid is less than K
        else if (mid < K) {
            if (smaller.size() == 0) {
                break;
            }
            ans[mid] = smaller.lastElement();
            smaller.remove(smaller.size()-1);
            low = mid + 1;
        }

        // If mid is greater than K
        else {
            if (greater.size() == 0) {
                break;
            }
            ans[mid] = greater.lastElement();
            greater.remove(greater.size()-1);
            high = mid - 1;
        }
    }

    // If f is -1
    if (f == -1) {
        System.out.println(-1 );
        return;
    }

    // Iterate in the range [1, N]
    for (int i = 0; i < N; i++) {

        // If ans[i] is equal to -1
        if (ans[i] == -1) {

            if (smaller.size()>0) {
                ans[i] = smaller.lastElement();
                smaller.remove(smaller.size()-1);
            }
            else if (greater.size()>0) {
                ans[i] = greater.lastElement();
                greater.remove(greater.size()-1);
            }
        }
    }

    // Print the rearranged array
    for (int i = 0; i < N; i++)
        System.out.print(ans[i] +" ");
    System.out.println();
}

  // Driver code
    public static void main(String args[])
    {

      // Input
    int arr[] = { 10, 7, 2, 5, 3, 8 };
    int K = 7;
    int N = arr.length;

    // Function Call
    Rearrange(arr, K, N);
    }
}

// This code is contributed by SoumikMondal
```

## 蟒蛇 3

```python
# Python 3 program for the above approach

# Function to rearrange the array
def Rearrange(arr, K,  N):

    # Stores the rearranged array
    ans = [0]*(N + 1)

    # Stores whether the arrangement
    # is possible or not
    f = -1

    for i in range(N):
        ans[i] = -1

    # Update K with the position of K
    K = arr.index(K)

    # Stores all elements lesser than
    # and greater than in vector smaller
    # and greater respectively
    smaller = []
    greater = []

    # Traverse the array arr[]
    for i in range(N):

        # If arr[i] is less than arr[K]
        if (arr[i] < arr[K]):
            smaller.append(arr[i])

        # Else
        elif (arr[i] > arr[K]):
            greater.append(arr[i])

    low = 0
    high = N - 1

    # Iterate unil low is less than or
    # equal to high
    while (low <= high):

        # Stores mid point
        mid = (low + high) // 2

        # If mid is equal to K
        if (mid == K):
            ans[mid] = arr[K]
            f = 1
            break

        # If mid is less than K
        elif (mid < K):
            if (len(smaller) == 0):
                break

            ans[mid] = smaller[-1]
            smaller.pop()
            low = mid + 1

        # If mid is greater than K
        else:
            if (len(greater) == 0):
                break

            ans[mid] = greater[-1]
            greater.pop()
            high = mid - 1

    # If f is -1
    if (f == -1):
        print(-1)
        return

    # Iterate in the range [1, N]
    for i in range(N):

        # If ans[i] is equal to -1
        if (ans[i] == -1):

            if (len(smaller)):
                ans[i] = smaller[-1]
                smaller.pop()

            elif (len(greater)):
                ans[i] = greater[-1]
                greater.pop()

    # Print the rearranged array
    for i in range(N):
        print(ans[i], end=" ")
    print()

# Driver Code
if __name__ == "__main__":

    # Input
    arr = [10, 7, 2, 5, 3, 8]
    K = 7
    N = len(arr)

    # Function Call
    Rearrange(arr, K, N)

    # This code is contributed by ukasp.
```

## C\#

```csharp
// C# program for the above approach
using System;
using System.Collections.Generic;

public class GFG
{

  // Function to rearrange the array
  static void Rearrange(int []arr, int K, int N)
  {

    // Stores the rearranged array
    int []ans = new int[N + 1];

    // Stores whether the arrangement
    // is possible or not
    int f = -1;

    for (int i = 0; i < N; i++) {
      ans[i] = -1;
    }

    // Update K with the position of K
    for (int i = 0; i < arr.Length; i++)
    {
      if (arr[i] == K)
      {
        K = i;
        break;
      }
    }

    // Stores all elements lesser than
    // and greater than in vector smaller
    // and greater respectively
    List<int> smaller = new List<int>();
    List<int> greater = new List<int>();

    // Traverse the array []arr
    for (int i = 0; i < N; i++) {

      // If arr[i] is less than arr[K]
      if (arr[i] < arr[K])
        smaller.Add(arr[i]);

      // Else
      else if (arr[i] > arr[K])
        greater.Add(arr[i]);
    }

    int low = 0, high = N - 1;

    // Iterate unil low is less than or
    // equal to high
    while (low <= high) {

      // Stores mid point
      int mid = (low + high) / 2;

      // If mid is equal to K
      if (mid == K) {
        ans[mid] = arr[K];
        f = 1;
        break;
      }

      // If mid is less than K
      else if (mid < K) {
        if (smaller.Count == 0) {
          break;
        }
        ans[mid] = smaller[smaller.Count-1];
        smaller.RemoveAt(smaller.Count-1);
        low = mid + 1;
      }

      // If mid is greater than K
      else {
        if (greater.Count == 0) {
          break;
        }
        ans[mid] = greater[greater.Count-1];
        greater.RemoveAt(greater.Count-1);
        high = mid - 1;
      }
    }

    // If f is -1
    if (f == -1) {
      Console.WriteLine(-1 );
      return;
    }

    // Iterate in the range [1, N]
    for (int i = 0; i < N; i++) {

      // If ans[i] is equal to -1
      if (ans[i] == -1) {

        if (smaller.Count>0) {
          ans[i] = smaller[smaller.Count-1];
          smaller.RemoveAt(smaller.Count-1);
        }
        else if (greater.Count>0) {
          ans[i] = greater[greater.Count-1];
          greater.RemoveAt(greater.Count-1);
        }
      }
    }

    // Print the rearranged array
    for (int i = 0; i < N; i++)
      Console.Write(ans[i] +" ");
    Console.WriteLine();
  }

  // Driver code
  public static void Main(String []args)
  {

    // Input
    int []arr = { 10, 7, 2, 5, 3, 8 };
    int K = 7;
    int N = arr.Length;

    // Function Call
    Rearrange(arr, K, N);
  }
}

// This code is contributed by Princi Singh
```

## java 描述语言

```
<script>
        // JavaScript program for the above approach

        // Function to rearrange the array
        function Rearrange(arr, K, N)
        {

            // Stores the rearranged array
            let ans = new Array(N + 1);

            // Stores whether the arrangement
            // is possible or not
            let f = -1;

            for (let i = 0; i < N; i++) {
                ans[i] = -1;
            }

            // Update K with the position of K
            for (let i = 0; i < arr.length; i++) {
                if (arr[i] == K) {
                    K = i;
                    break;
                }
            }

            // Stores all elements lesser than
            // and greater than in vector smaller
            // and greater respectively
            let smaller = [];
            let greater = [];

            // Traverse the array arr[]
            for (let i = 0; i < N; i++) {

                // If arr[i] is less than arr[K]
                if (arr[i] < arr[K])
                    smaller.push(arr[i]);

                // Else
                else if (arr[i] > arr[K])
                    greater.push(arr[i]);
            }

            let low = 0, high = N - 1;

            // Iterate unil low is less than or
            // equal to high
            while (low <= high) {

                // Stores mid point
                let mid = Math.floor((low + high) / 2);

                // If mid is equal to K
                if (mid == K) {
                    ans[mid] = arr[K];
                    f = 1;
                    break;
                }

                // If mid is less than K
                else if (mid < K) {
                    if (smaller.length == 0) {
                        break;
                    }
                    ans[mid] = smaller[smaller.length - 1];
                    smaller.pop();
                    low = mid + 1;
                }
                // If mid is greater than K
                else {
                    if (greater.length == 0) {
                        break;
                    }
                    ans[mid] = greater[greater.length - 1];
                    greater.pop();
                    high = mid - 1;
                }
            }

            // If f is -1
            if (f == -1) {
                document.write(-1);
                return;
            }

            // Iterate in the range [1, N]
            for (let i = 0; i < N; i++) {

                // If ans[i] is equal to -1
                if (ans[i] == -1) {

                    if (smaller.length != 0) {
                        ans[i] = smaller[smaller.length - 1];
                        smaller.pop();
                    }
                    else if (greater.length != 0) {
                        ans[i] = greater[greater.length - 1];
                        greater.pop;
                    }
                }
            }

            // Print the rearranged array
            for (let i = 0; i < N; i++)
                document.write(ans[i] + " ");
            document.write("<br>")
        }

        // Driver Code

        // Input
        let arr = [10, 7, 2, 5, 3, 8];
        let K = 7;
        let N = arr.length;

        // Function Call
        Rearrange(arr, K, N);

// This code is contributed by Potta Lokesh
    </script>
```

**Output**

```
3 7 8 5 2 10 
```

`时间复杂度:` `O(N)`
`辅助空间:` `O(N)`