# 根据给定的条件从数组中构造一个 K 长度的二进制字符串

> 原文: [https://www.geeksforgeeks.org/construct-a-k-length-binary-string-from-an-array-based-on-given-conditions/](https://www.geeksforgeeks.org/construct-a-k-length-binary-string-from-an-array-based-on-given-conditions/)

给定一个由 `N` 个整数和一个整数 `K` 组成的数组 `arr[]`，任务是构造一个长度为 `K` 的二进制字符串，满足以下条件:

1.  如果可以从数组中形成具有和的子集 `i`，则 `i` 索引处的字符为 `'1'`。
2.  否则，`i` 索引处的字符为 `'0'`。

**示例:**

> **输入:** `arr[] = {1，4}`，`K = 5`
> **输出:** `10011`
> **说明:**
> 第 1 个索引处的字符可以考虑子集 `{1}` 通过 `'1'` 来制作。
> 考虑到子集 `{4}`，第 4 个索引处的字符可以由 `'1'` 构成。
> 考虑到子集 `{1，4}`，第 5 个索引处的字符可以由 `'1'` 构成。

> **输入:** `arr[] = {1，6，1}`，`K = 8`
> **输出:** `11000111`

## 方法

思路是用一种贪婪的方法来解决这个问题。以下是步骤:

*   初始化大小为 `10^5 + 5` 的位集 `bitset`，表示 `bit[]`，并将 `bit[0] = 1`。
*   遍历数组，对于每个数组元素 `arr[i]`，更新 `bit` 为 `bit |= bit << arr[i]`，使得 `bit` 中为 `1` 的位 `p` 表示 `p` 可以作为子集和获得。
*   在第 `i` 次迭代，`bit[i]` 存储初始和，并且在执行 `bit << arr[i]` 之后，所有位被 `arr[i]` 移位。因此，位 `p` 变成了 `p + arr[i]`。
*   最后，`bit | (bit << arr[i])` 合并这两种情况，是否考虑第 `i` 个位置。
*   从 `1` 迭代到 `K` 并将每个值 `bit[i]` 打印为所需的二进制字符串。

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// To construct the required binary string
bitset<100003> bit;

// Function to construct binary string
// according to the given conditions
void constructBinaryString(int arr[], int N, int K)
{
    // Initialize with 1
    bit[0] = 1;

    // Traverse the array
    for (int i = 0; i < N; i++) {
        // To check if the i-th integer
        // needs to be considered or not
        bit |= bit << arr[i];
    }

    // Print the binary string
    for (int i = 1; i <= K; i++) {
        cout << bit[i];
    }
}

// Driver Code
int main()
{
    // Given array
    int arr[] = { 1, 6, 1 };

    // Size of the array
    int N = sizeof(arr) / sizeof(arr[0]);

    // Given K
    int K = 8;

    constructBinaryString(arr, N, K);
}
```

### Python 3

```python
# Python program for the above approach

# Function to construct binary string
# according to the given conditions
def constructBinaryString(arr, N, K):
    # Initialize with 1
    bit = 1

    # Traverse the array
    for i in range(0, N):
        # To check if the i-th integer
        # needs to be considered or not
        bit |= bit << arr[i]

    # Print the binary string
    bit = bin(bit).replace("0b", "")
    print(bit[1:K + 1])

# Driver Code
# Given array
arr = [1, 6, 1]

# Size of the array
N = len(arr)

# Given K
K = 8

constructBinaryString(arr, N, K)

# This code is contributed by shubhamsingh10
```

**输出:**

```
11000111
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(N)`