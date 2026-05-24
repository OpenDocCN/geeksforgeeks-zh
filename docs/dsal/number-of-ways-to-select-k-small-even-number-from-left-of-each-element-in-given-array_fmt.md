# 在给定数组中从每个元素左侧选择 K 个小偶数的方式数

> 原文：[https://www.geeksforgeeks.org/number-of-ways-to-select-k-small-even-number-from-left-of-each-element-in-given-array/](https://www.geeksforgeeks.org/number-of-ways-to-select-k-small-even-number-from-left-of-each-element-in-given-array/)

给定一个[数组](https://www.geeksforgeeks.org/introduction-to-arrays/) `arr[]`，由 `N` 个不同的整数和一个正整数 `K` 组成，任务是找到若干方法来从每一个第 `i` 位置的左侧选择 `K` 元素，使得元素满足条件。

**例：**

> **输入：** `arr[] = {4，2，12，33}`，`K = 2`
> **输出：** `0 0 1 3`
> **解释：**
>
> 1.  对于 `arr[0](=4)`，有 0 个小于 `arr[i]` 的偶数元素。因此，从 0 个元素中选择 2 个元素的方式等于 `C(0，2) = 0`。
> 2.  对于 `arr[1](=2)`，有 0 个小于 `arr[i]` 的偶数元素。因此，从 0 个元素中选择 2 个元素的方式等于 `C(0，2) = 0`。
> 3.  对于 `arr[2](=12)`，有 2 个小于 `arr[i]` 的偶数元素。因此，从 2 个元素中选择 2 个元素的方式等于 `C(2，2)` 是 1。
> 4.  对于 `arr[3](=33)`，有 3 个小于 `arr[i]` 的偶数元素。因此，从 3 个元素中选择 2 个元素的方式等于 `C(3，2)` 是 3。
>
> **输入：** `arr[] = {1，2，3}`，`K = 2`
> **输出：** `0 0 1`

**天真法：** 最简单的方法是[遍历数组](https://www.geeksforgeeks.org/c-program-to-traverse-an-array/)，对于每个元素找到所有小于给定元素的偶数，检查计数是否小于 `K`，然后打印 `0`，否则，使用[组合学](https://www.geeksforgeeks.org/combinatorics-gq/)找到方式数。

**时间复杂度：** `O(N^2)`
**辅助空间：** `O(1)`

**高效方法：** 上述方法可以通过使用[有序集数据结构](https://www.geeksforgeeks.org/ordered-set-gnu-c-pbds/)来优化。按照以下步骤解决问题：

*   初始化一个[有序集](https://www.geeksforgeeks.org/ordered-set-gnu-c-pbds/)，比如说 `S` 来存储偶数的值。
*   另外，初始化一个数组，比如说 `ans[]`，来存储结果。
*   [使用变量 `i` 遍历数组](https://www.geeksforgeeks.org/c-program-to-traverse-an-array/) `arr[]`，并执行以下步骤：
    *   如果集合 `S` 的大小是 `0`，那么将 `0` 分配给 `ans[i]` 并[继续](https://www.geeksforgeeks.org/continue-statement-cpp/)。
    *   使用集合 `S` 中的 [`order_of_key()`](https://www.geeksforgeeks.org/order_of_key-in-c/) 函数找到小于 `arr[i]` 的元素计数，并将其存储在一个变量中，比如说 `count`。
    *   现在将从 `count` 中选择 `K` 个元素的方式计数，即 `C(count，K)`，分配给 `ans[i]`。
*   最后，完成以上步骤后，[打印数组](https://www.geeksforgeeks.org/c-program-to-print-an-array-using-recursion/) `ans[]`。

下面是上述方法的实现：

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Policy based data structure
#include <ext/pb_ds/assoc_container.hpp>
#include <ext/pb_ds/tree_policy.hpp>
using namespace __gnu_pbds;

#define ordered_set \
    tree<int, null_type, less<int>, rb_tree_tag, \
         tree_order_statistics_node_update>

// NCR formula to find number
// of ways
int ncr(int n, int r)
{
    if (r == 0 || n == r) {
        return 1;
    }
    return ncr(n - 1, r) + ncr(n - 1, r - 1);
}

// Function to find the number of ways
// of selecting K smaller even element
// on the left of each element
void numberofSmallerElementsInLeft(int arr[], int N, int K)
{
    // Set to store even elements
    ordered_set S;

    // Stores answer for each element
    int ans[N];

    for (int i = 0; i < N; i++) {
        // Set is empty
        if (S.size() == 0)
            ans[i] = 0;
        else {

            // Finds the count of elements
            // less than arr[i]
            int count = S.order_of_key(arr[i]);

            // If count is 0
            if (count == 0)
                ans[i] = 0;
            // Else
            else {

                // Number of ways to choose k
                // elements from pos
                ans[i] = ncr(count, K);
            }
        }

        // If the element is even
        // insert it into S
        if (arr[i] % 2 == 0)
            S.insert(arr[i]);
    }
    // Print the result
    for (int i = 0; i < N; i++) {
        cout << ans[i] << " ";
    }
}

// Driver Code
int main()
{

    // Input
    int arr[] = { 4, 2, 12, 33 };
    int K = 2;
    int N = sizeof(arr) / sizeof(arr[0]);

    // Function Call
    numberofSmallerElementsInLeft(arr, N, K);
    return 0;
}
```

**输出**

```
0 0 1 3
```

**时间复杂度：** `O(N*log(N))`
**辅助空间：** `O(N)`