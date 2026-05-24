# 求给定矩阵可以形成的角矩形的个数

> 原文：[https://www.geeksforgeeks.org/find-the-number-of-corner-rectangles-that-can-be-formed-from-given-matrix/](https://www.geeksforgeeks.org/find-the-number-of-corner-rectangles-that-can-be-formed-from-given-matrix/)

给定尺寸为 `N*M` 的二元矩阵 `mat[][]`，任务是找出可以形成的角矩形的数量。角矩形被定义为在其角上具有 `1s` 的子矩阵，并且每个 `1s` 必须属于该子矩阵中的唯一单元。

**示例：**

> **输入：** `mat[][] = {{1，0，1}，{0，0，0}，{1，0，1}}`
> **输出：** 1
> **解释：**
> 满足给定公式的子矩阵只有一个，用粗体表示为：
> **1**0**1**
> 0 0
> **1**0**1**

> **输入：** `mat[][] = {{1，1，1}，{1，1，1}，{1，1，1}}`
> **输出：** 9

**方法：** 给定的问题可以通过使用来自 N 个点的所有不同的可能对的概念来解决，所述 N 个点由 `^N C_2` 给出。其思想是将数值为 `1s` 的一对单元格 `(i，j)` 的频率存储在一对的图中，比如说 `M`。生成频率图后，找到使用上述公式形成的角矩形的总数。按照以下步骤解决给定的问题：

*   初始化一个变量，比如 `count`，它存储角矩形的结果计数。
*   初始化一个映射，比如说 `m[]` 存储单元格 `(i，j)` 的频率，取值为 `1`。
*   使用变量 `i` 迭代范围 `[0，M)`，并执行以下任务：
    *   使用变量 `j` 迭代范围 `[0，N]`，如果 `mat[i][j]` 等于 `1`，则使用变量 `k` 迭代范围 `[j+1，N]`，如果 `mat[i][k]` 的值等于 `1`，则增加 `m[{j，k}]`。
*   使用变量 `it` 遍历地图 `m[]`，并将 `it.second * (it.second - 1) / 2` 的值添加到变量 `count` 中。
*   执行上述步骤后，打印 `count` 的值作为答案。

下面是上述方法的实现：

## C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to find all possible rectangles
// having distinct corners as 1s
int countCornerRectangles(vector<vector<int>>& mat)
{
    // Stores the count of rectangles
    int count = 0;

    int N = mat.size();
    int M = mat[0].size();

    // Map to store the frequency
    map<pair<int, int>, int> m;

    // Iterate over each row
    for (int i = 0; i < N; i++) {

        // Iterate over each cell
        for (int j = 0; j < M; j++) {
            if (mat[i][j] == 1) {

                // Check for 1's of the
                // same column pair
                for (int k = j + 1; k < M; k++) {
                    if (mat[i][k] == 1) {
                        m[{j, k}]++;
                    }
                }
            }
        }
    }

    // For any pair of column cells (x, y)
    // If the frequency is n. Then choosing
    // any 2 will form a rectangle
    for (auto& it : m) {
        count += (it.second * (it.second - 1)) / 2;
    }

    return count;
}

// Driver Code
int main()
{
    vector<vector<int>> mat
        = { { 1, 1, 1 }, { 1, 1, 1 }, { 1, 1, 1 } };

    cout << countCornerRectangles(mat);

    return 0;
}
```

**Output:**

```
9
```

**时间复杂度：** `O(N * M^2)`
**辅助空间：** `O(M^2)`