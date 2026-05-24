# 从给定的两个数组中找到子数组，使它们具有相等的和

> 原文：[https://www.geeksforgeeks.org/find-sub-arrays-from-given-two-arrays-such-that-they-have-equal-sum/](https://www.geeksforgeeks.org/find-sub-arrays-from-given-two-arrays-such-that-they-have-equal-sum/)

给定两个大小相等的数组 `A[]` 和 `B[]`，即 `N`，包含从 `1` 到 `N` 的整数。任务是从给定的数组中找到子数组，使它们具有相等的和。打印这些子数组的索引。如果没有这样的子数组，则打印 `-1`。

**示例：**

> **输入：** `A[] = {1, 2, 3, 4, 5}`，`B[] = {6, 2, 1, 5, 4}`
> **输出：**
> 数组 1 中的索引：0, 1, 2
> 数组 2 中的索引：0
> `A[0..2] = 1 + 2 + 3 = 6`
> `B[0] = 6`
>
> **输入：** `A[] = {10, 1}`，`B[] = {5, 3}`
> **输出：** `-1`
> 没有这样的子数组。

**逼近：** 让 `A_i` 表示 `A` 中前 `i` 个元素之和，`B_j` 表示 `B` 中前 `j` 个元素之和。不失一般性，我们假设 `A_n <= B_n`。
现为 `B_n = A_n = A_i`。所以对于每一个 `A_i`，我们可以找到最小的 `j` 使得 `A_i = B_j`。对于每一个 `i`，我们都找到了区别 `B_j - A_i`。
如果差值为 0，那么我们就完成了，因为 `A` 中的 `1` 到 `i` 和 `B` 中的 `1` 到 `j` 具有相同的和。假设差值不为 0。那么差别一定在 `[1, n-1]` 的范围内。

> **证明：**
> 让 `B_j - A_i = n`
> `B_j = A_i + n`
> `B_{j-1} = A_i` (由于 `B` 中的第 `j` 个元素最多可以为 `n`，所以 `B_j = B_{j-1} + n`)
> 这是一个矛盾，因为我们假设 `j` 是最小的指数，使得 `B_j >= A_i` 就是 `j`，所以我们的假设是错误的。
> 所以 `B_j - A_i < n`

现在有 `n` 个这样的差异（对应于每个指数），但只有 `(n-1)` 个可能的值，所以至少两个指数会产生相同的差异（根据鸽子洞原理）。让 `A_j - B_y = A_i - B_x`。重新排列后，我们得到 `A_j - A_i = B_y - B_x`。所以需要的子数组是 `A` 中的 `[i+1, j]` 和 `B` 中的 `[x+1, y]`。

下面是上述方法的实现：

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function to print the valid indices in the array
void printAns(int x, int y, int num)
{
    cout << "Indices in array " << num << " : ";
    for (int i = x; i < y; ++i) {
        cout << i << ", ";
    }
    cout << y << "\n";
}

// Function to find sub-arrays from two
// different arrays with equal sum
void findSubarray(int N, int a[], int b[], bool swap)
{
    // Map to store the indices in A and B
    // which produce the given difference
    std::map<int, pair<int, int> > index;
    int difference;
    index[0] = make_pair(-1, -1);
    int j = 0;
    for (int i = 0; i < N; ++i) {
        // Find the smallest j such that b[j] >= a[i]
        while (b[j] < a[i]) {
            j++;
        }
        difference = b[j] - a[i];
        // Difference encountered for the second time
        if (index.find(difference) != index.end()) {
            // b[j] - a[i] = b[idx.second] - a[idx.first]
            // b[j] - b[idx.second] = a[i] = a[idx.first]
            // So sub-arrays are a[idx.first+1...i] and b[idx.second+1...j]
            if (swap) {
                pair<int, int> idx = index[b[j] - a[i]];
                printAns(idx.second + 1, j, 1);
                printAns(idx.first + 1, i, 2);
            }
            else {
                pair<int, int> idx = index[b[j] - a[i]];
                printAns(idx.first + 1, i, 1);
                printAns(idx.second + 1, j, 2);
            }
            return;
        }
        // Store the indices for difference in the map
        index[difference] = make_pair(i, j);
    }
    cout << "-1";
}

// Utility function to calculate the
// cumulative sum of the array
void cumulativeSum(int arr[], int n)
{
    for (int i = 1; i < n; ++i)
        arr[i] += arr[i - 1];
}

// Driver code
int main()
{
    int a[] = { 1, 2, 3, 4, 5 };
    int b[] = { 6, 2, 1, 5, 4 };
    int N = sizeof(a) / sizeof(a[0]);
    // Function to update the arrays
    // with their cumulative sum
    cumulativeSum(a, N);
    cumulativeSum(b, N);
    if (b[N - 1] > a[N - 1]) {
        findSubarray(N, a, b, false);
    }
    else {
        // Swap is true as a and b are swapped during
        // function call
        findSubarray(N, b, a, true);
    }
    return 0;
}
```

## Python 3

```python
# Python3 implementation of the approach

# Function to print the valid indices in the array
def printAns(x, y, num):
    print("Indices in array", num, ":", end = " ")
    for i in range(x, y):
        print(i, end = ", ")
    print(y)

# Function to find sub-arrays from two
# different arrays with equal sum
def findSubarray(N, a, b, swap):
    # Map to store the indices in A and B
    # which produce the given difference
    index = {}
    difference, j = 0, 0
    index[0] = (-1, -1)
    for i in range(0, N):
        # Find the smallest j such that b[j] >= a[i]
        while b[j] < a[i]:
            j += 1
        difference = b[j] - a[i]
        # Difference encountered for the second time
        if difference in index:
            # b[j] - a[i] = b[idx.second] - a[idx.first]
            # b[j] - b[idx.second] = a[i] = a[idx.first]
            # So sub-arrays are a[idx.first+1...i] and b[idx.second+1...j]
            if swap:
                idx = index[b[j] - a[i]]
                printAns(idx[1] + 1, j, 1)
                printAns(idx[0] + 1, i, 2)
            else:
                idx = index[b[j] - a[i]]
                printAns(idx[0] + 1, i, 1)
                printAns(idx[1] + 1, j, 2)
            return
        # Store the indices for difference in the map
        index[difference] = (i, j)
    print("-1")

# Utility function to calculate the
# cumulative sum of the array
def cumulativeSum(arr, n):
    for i in range(1, n):
        arr[i] += arr[i - 1]

# Driver code
if __name__ == "__main__":
    a = [1, 2, 3, 4, 5]
    b = [6, 2, 1, 5, 4]
    N = len(a)
    # Function to update the arrays
    # with their cumulative sum
    cumulativeSum(a, N)
    cumulativeSum(b, N)
    if b[N - 1] > a[N - 1]:
        findSubarray(N, a, b, False)
    else:
        # Swap is true as a and b are
        # swapped during function call
        findSubarray(N, b, a, True)

# This code is contributed by Rituraj Jain
```

**Output：**

```
Indices in array 1 : 0, 1, 2
Indices in array 2 : 0
```