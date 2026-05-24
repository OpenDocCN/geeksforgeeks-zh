# 根据每个节点的组件大小构建一个图

> 原文：[https://www.geeksforgeeks.org/construct-a-graph-from-size-of-components-for-each-node/](https://www.geeksforgeeks.org/construct-a-graph-from-size-of-components-for-each-node/)

给定大小为 `N` 的数组 `A[]`，对于范围 `[0, N]` 中的每个索引 `i`，值 `A[i]` 表示节点 `i` 的连通组件的大小。任务是为可能的图找到边，否则打印 `-1`。

> **注意：** 每个数组可能有 1 个以上的可能答案。打印其中任何一个。

**示例：**

> **输入：** `N = 5`，`A[] = {2, 1, 1, 2, 1}`
> **输出：** `{{0, 3}}`
> **说明：** 节点(0, 3)的连通分量大小为 2，每隔一个节点为单数。
>
> **输入：** `N = 4`，`A[] = {2, 2, 2, 2}`
> **输出：** `{{0, 1}, {2, 3}}`
> **解释：** 其他可能的变化有 – `{{0, 2}, {1, 3}}`, `{{0, 3}, {1, 2}}`
>
> **输入：** `N=2`，`A[] = {1, 1}`
> **输出：** 图形已经连接。
> **说明：** 由于每个连接的组件大小为 1，因此不需要边来连接任何一对节点。

## 方法

想法是观察所有相同的组件大小可以使用等于数组值大小的总节点相互连接。因此，将所有具有相同索引值的节点存储到地图中。节点的值可以用地图结构 `map<int, vector<int>>` 来存储。检查连接组件的每个大小，相应的总节点数是该大小的倍数。如果对于任何连接的组件，上述条件失败，那么将没有有效的图形。立即返回 `-1`。否则，对于所有多个存储顶点，并相邻地连接它们。存储数组中的所有边并输出结果。按照以下步骤解决问题：

*   初始化一个布尔变量 `flag` 标记为 `false` 以检查是否所有的值都是 `1`。如果是，那么就不需要形成任何边缘。
*   初始化向量图 `mp[]` 以存储特定连接组件大小的索引。
*   使用变量 `i` 迭代范围 `[0, N)`，并执行以下任务：
    *   将值 `i` 推送到地图中 `A[i]` 处的向量中。
    *   如果 `A[i]` 不等于 `1`，则将标志值设置为 `true`。
*   如果 `flag` 为 `false`，则返回。
*   使用变量 `x` 迭代地图，并执行以下任务：
    *   如果 `x.second.size()` 不能被 `x.first` 整除，则打印 `-1` 并返回 `0`。
*   初始化一对的 int `边[]` 的向量来存储边。
*   使用变量 `x` 迭代地图，并执行以下任务：
    *   初始化一个向量 `节点[]` 作为当前位置的向量。
    *   循环迭代直到 `节点的大小[]` 大于 `0` 并执行以下任务：
        *   将变量 `cnt` 初始化为 `0`。
        *   初始化向量 `组件节点[]`。
        *   循环迭代直到 `cnt` 不等于 `x.first` 并执行以下任务：
            *   将向量 `节点[]` 中的最新值推入向量 `组件节点[]` 中，并从 `节点[]` 弹出该值，并将 `cnt` 的值增加 `1`。
        *   使用变量 `i` 迭代范围 `[1, component_nodes.size())`，并执行以下任务：
            *   将对 `{component_nodes[i], component_nodes[i-1]}` 推入向量 `边[]`。
*   执行上述步骤后，打印矢量 `边[]` 作为答案。

下面是上述方法的实现：

## C++

```cpp
// C++ Program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to construct the graph for
// the given array
int constructConnectedComponent(int A[], int N)
{

    // Variable to check if all the values
    // are 1, then no need to form any edge
    bool flag = false;

    // Iterate through the array and store
    // the indices in a
    // map of same size connected component
    map<int, vector<int> > mp;
    for (int i = 0; i < N; i++) {
        mp[A[i]].push_back(i);
        if (A[i] != 1)
            flag = true;
    }

    if (!flag) {
        cout << "Graph already connected.\n";
        return 0;
    }

    // Check if the total size of vector is a
    // multiple of size
    for (auto x : mp) {
        if ((x.second).size() % x.first != 0) {
            cout << -1;
            return 0;
        }
    }

    // Make a vector to store the edges
    vector<pair<int, int> > edges;

    // Start constructing edges with each multiple
    // from the corresponding vector
    for (auto x : mp) {
        vector<int> nodes = x.second;
        while (!nodes.empty()) {
            int cnt = 0;
            vector<int> component_nodes;
            while (cnt != x.first) {
                component_nodes.push_back(nodes.back());
                nodes.pop_back();
                cnt++;
            }

            // Make edges between selected node
            for (int i = 1; i < component_nodes.size();
                 i++) {
                edges.push_back(
                    make_pair(component_nodes[i],
                              component_nodes[i - 1]));
            }
        }
    }

    // Print the edges of the graph
    cout << "[";
    for (int i = 0; i < edges.size(); i++) {
        cout << "{" << edges[i].first << ", "
             << edges[i].second << "}";
        if (i != edges.size() - 1) {
            cout << ", ";
        }
    }
    cout << "]";

    return 0;
}

// Driver Code
int main()
{
    int N = 5;
    int A[] = { 2, 1, 1, 2, 1 };

    constructConnectedComponent(A, N);

    return 0;
}
```

**Output:**

```
[{0, 3}]
```

时间复杂度：`O(N*log(N))`
辅助空间：`O(N)`