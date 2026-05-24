# 检查满足给定条件的图中是否存在长度为 3 的循环

> 原文: [https://www.geeksforgeeks.org/check-if-a-cycle-of-length-3-exists-or-not-in-a-graph-that-satisfy-a-given-condition/](https://www.geeksforgeeks.org/check-if-a-cycle-of-length-3-exists-or-not-in-a-graph-that-satisfy-a-given-condition/)

给定一个表示图的节点的整数数组 `Arr[]` 和 `N`。边缘定义在那些其[位“与”](https://www.geeksforgeeks.org/bitwise-operators-in-c-cpp/)不等于 `零` 的对之间。任务是找出图中是否存在长度为 3 的循环。

## 举例:

> **输入:** `Arr[] = {26, 33, 35, 40, 50}`
> **输出:** 是
> 26，33，50 之间存在循环。
> **输入:** `Arr[] = {17, 142, 243, 300}`
> **输出:** 否

## 天真方法:

运行嵌套循环，检查每对之间是否存在边(如果它们的按位“与”值为非零)。因此，我们形成整个图，并通过使用任何[循环检测](https://www.geeksforgeeks.org/detect-cycle-undirected-graph/)方法来检查该图中是否存在循环。

## 高效方法:

*   通过连接至少 `3 个`边形成一个循环。
*   这个想法是制作一个 2D 数组，其中第 `i` 行存储 `Arr[i]`的二进制值。
*   接下来，以列的方式循环，检查是否存在 1 的数量至少为 3 的列。
    *   如果是这样的话，就意味着图中存在一个循环。
    *   如果不存在这样的列，则意味着图中没有循环。

> `Arr[] = {26, 33, 35, 40, 50}`
> 2D 阵列如下
> `bi =`
> `[0 1 0 1 0 0 0 0 0],`
> `[1 0 0 0 1 0 0 0],`
> `[1 1 0 0 1 0 0],`
> `[0 0 0 1 0 1 0 1 0],`
> `[0 1 0 1 1 0 0],`
>
> `bi[0][1]`，`bi[2][1]`和 `bi[4][1]` 是 1。这意味着以下对(`Arr[0]`、`Arr[2]`)、(`Arr[2]`、`Arr[4]`)、(`Arr[0]`、`Arr[4]`)的按位“与”值不为零。这 3 条边形成一个循环。

以下是上述方法的实现:

```cpp
// C++ program to check if a cycle of length 3
// exists or not in a graph that satisfy a given condition
#include <bits/stdc++.h>
using namespace std;

// Function to check if a cycle of length 3 exists or not
string isCycle(int n, int arr[])
{
    // To store the binary value of array elements
    vector<vector<int> > bi(n, vector<int>(32, 0));

    // Converting array elements into binary
    for (int i = 0; i < n; i++) {
        int k = 0;
        int num = arr[i];
        while (num > 0) {
            bi[i][k] = num % 2;
            num /= 2;
            k++;
        }
    }

    // Traversing column-wise
    for (int i = 0; i < 32; i++) {
        int cnt = 0;

        // Counting 1's in a column
        for (int j = 0; j < n; j++) {
            if (bi[j][i] == 1)
                cnt++;
        }

        // If 1's are at least 3, then cycle exists
        if (cnt >= 3)
            return "Yes";
    }

    // Otherwise, cycle does not exist
    return "No";
}

// Driver Code
int main()
{
    int arr[] = { 26, 33, 35, 40, 50 };
    int N = sizeof(arr) / sizeof(arr[0]);

    cout << isCycle(N, arr);

    return 0;
}
```

**Output:**

```
Yes
```