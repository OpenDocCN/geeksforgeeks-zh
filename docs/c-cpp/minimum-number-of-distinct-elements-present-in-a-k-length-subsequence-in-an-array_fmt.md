# 数组中K长度子序列中不同元素的最小数量

> 原文：[https://www.geeksforgeeks.org/minimum-number-of-distinct-elements-present-in-a-k-length-subsequence-in-an-array/](https://www.geeksforgeeks.org/minimum-number-of-distinct-elements-present-in-a-k-length-subsequence-in-an-array/)

给定一个由 `N` 个整数和一个整数 `K` 组成的数组 `A[]`，任务是计算给定数组 `A` 的长度为 `K` 的子序列中存在的不同元素的最小数量。

**示例：**

> **输入：** `A = {3, 1, 3, 2, 3, 4, 5, 4}`，`K = 4`
> **输出：** 2
> **解释：** 包含最小数目的相异元素的长度 4 的子序列是 `{3, 3, 3, 4}`，由 2 个相异元素组成，即 `{3, 4}`。
>
> **输入：** `A = {3, 1, 3, 2, 3, 4, 5, 4}`，`K = 5`
> **输出：** 2
> **解释：** 包含最小数量的相异元素的长度 5 的子序列是 `{3, 3, 3, 4, 4}`，由 2 个相异元素组成，即 `{3, 4}`。

**天真方法：** 最简单的方法是生成所有长度的子序列 `K`，对于每个子序列，找到其中存在的不同元素个数。最后，打印存在的最小数量的不同元素。

**时间复杂度：** `O(K * N^K)`
**辅助空间：** `O(N)`

**高效方法：** 上述方法可以使用哈希进行优化。按照以下步骤解决问题：

*   存储给定数组中所有元素的频率，`A[]` 在 `HashMap` 中，说 `M`。
*   遍历散列表 `M`，推另一个阵中的频率，说 `V`。
*   按降序排列数组 `V`。
*   初始化两个变量 `cnt` 和 `len` 为 `0`，以存储所需的结果和由此形成的子序列的长度。
*   遍历阵 `V` 使用一个变量，说 `i`。
    *   如果 `len` 的值 `≥ K`，则脱离回路。
    *   否则，将 `len` 的值增加 `V[i]`，将 `cnt` 的值增加 `1`。
*   完成上述步骤后，打印 `cnt` 的值作为结果。

下面是上述方法的实现：

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to count the minimum number
// of distinct elements present in any
// subsequence of length K of the given array
void findMinimumDistinct(int A[], int N, int K)
{

    // Stores the frequency
    // of each array element
    unordered_map<int, int> mp;

    // Traverse the array
    for (int i = 0; i < N; i++)

        // Update frequency
        // of array elements
        mp[A[i]]++ ;

    // Store the required result
    int count = 0;

    // Store the length of the
    // required subsequence
    int len = 0;

    // Store the frequencies
    // in decreasing order
    vector<int> counts;

    // Traverse the map
    for (auto i : mp)

        // Push the frequencies
        // into the HashMap
        counts.push_back(i.second);

    // Sort the array in decreasing order
    sort(counts.begin(), counts.end(),
         greater<int>());

    // Add the elements into the subsequence
    // starting from one with highest frequency
    for (int i = 0; i < counts.size(); i++) {

        // If length of subsequence is >= k
        if (len >= K)
            break;
        len += counts[i];
        count++ ;
    }

    // Print the result
    cout << count;
}

// Driver Code
int main()
{
    int A[] = { 3, 1, 3, 2, 3, 4, 5, 4 };
    int K = 4;

    // Store the size of the array
    int N = sizeof(A) / sizeof(A[0]);

    // Function Call to count minimum
    // number of distinct elmeents
    // present in a K-length subsequence
    findMinimumDistinct(A, N, K);

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.util.*;

class GFG{

    // Function to count the minimum number
    // of distinct elements present in any
    // subsequence of length K of the given array
    static void findMinimumDistinct(int A[], int N, int K)
    {

        // Stores the frequency
        // of each array element
        Map<Integer, Integer> mp = new HashMap<>();

        // Traverse the array
        for(int i = 0; i < N; i++)

            // Update frequency
            // of array elements
            mp.put(A[i], mp.getOrDefault(A[i], 0) + 1);

        // Store the required result
        int count = 0;

        // Store the length of the
        // required subsequence
        int len = 0;

        // Store the frequencies
        // in decreasing order
        ArrayList<Integer> counts = new ArrayList<>();

        // Traverse the map
        for(Map.Entry<Integer, Integer> i : mp.entrySet())

            // Push the frequencies
            // into the HashMap
            counts.add(i.getValue());

        // Sort the array in decreasing order
        Collections.sort(counts, (a, b) -> b - a);

        // Add the elements into the subsequence
        // starting from one with highest frequency
        for(int i = 0; i < counts.size(); i++)
        {

            // If length of subsequence is >= k
            if (len >= K)
                break;

            len += counts.get(i);
            count++ ;
        }

        // Print the result
        System.out.print(count);
    }

    // Driver code
    public static void main(String[] args)
    {
        int A[] = { 3, 1, 3, 2, 3, 4, 5, 4 };
        int K = 4;

        // Store the size of the array
        int N = A.length;

        // Function Call to count minimum
        // number of distinct elmeents
        // present in a K-length subsequence
        findMinimumDistinct(A, N, K);
    }
}

// This code is contributed by offbeat
```

## Python 3

```python
# Python3 program for the above approach
from collections import Counter

# Function to count the minimum number
# of distinct elements present in any
# subsequence of length K of the given array
def findMinimumDistinct(A, N, K):

    # Stores the frequency
    # of each array element
    mp = Counter(A)

    # Store the required result
    count = 0

    # Store the length of the
    # required subsequence
    length = 0

    # Store the frequencies
    # in decreasing order
    counts = []

    # Traverse the map
    for i in mp:

        # Push the frequencies
        # into the HashMap
        counts.append(mp[i])

    # Sort the array in decreasing order
    counts = sorted(counts)
    counts.reverse()

    # Add the elements into the subsequence
    # starting from one with highest frequency
    for i in range(len(counts)):

        # If length of subsequence is >= k
        if (length >= K):
            break

        length += counts[i]
        count += 1

    # Print the result
    print(count)

# Driver Code
A = [3, 1, 3, 2, 3, 4, 5, 4]
K = 4

# Store the size of the array
N = len(A)

# Function Call to count minimum
# number of distinct elmeents
# present in a K-length subsequence
findMinimumDistinct(A, N, K)

# This code is contributed by sudhanshugupta2019a
```

**Output:**

```
2
```

**时间复杂度：** `O(N*log(N))`
**辅助空间：** `O(N)`