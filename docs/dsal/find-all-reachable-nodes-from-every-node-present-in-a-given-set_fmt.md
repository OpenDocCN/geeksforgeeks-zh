# 从给定集合中存在的每个节点中查找所有可达节点

> 原文： [https://www.geeksforgeeks.org/find-all-reachable-nodes-from-every-node-present-in-a-given-set/](https://www.geeksforgeeks.org/find-all-reachable-nodes-from-every-node-present-in-a-given-set/)

给定一个无向图和一组顶点，从给定集中存在的每个顶点中找到所有可到达的节点。

考虑下面具有 2 个未连通组件的无向图。

![GraphEx1](img/7f4cdf40d66fc20a674b0c5b7ac379f8.png)

```
arr[] = {1 , 2 , 5}
Reachable nodes from 1 are  1, 2, 3, 4
Reachable nodes from 2 are 1, 2, 3, 4
Reachable nodes from 5 are 5, 6, 7
```

## 方法 1 (简单)

一个直接的解决方案是对集合中存在的每个节点执行一次 [BFS 遍历](https://www.geeksforgeeks.org/breadth-first-traversal-for-a-graph/)，然后找到所有可到达的节点。

假设我们需要为 `n` 个节点查找可达节点，此解决方案的时间复杂度为 `O(n*(V+E))`，其中 `V` 是图中的节点数，`E` 是图中的边数。请注意，我们需要为每个节点单独调用 `BFS`，而不能使用之前遍历的 `visited` 数组，因为同一个顶点可能需要被打印多次。这看起来是一个有效的解决方案，但考虑当 `E = Θ(V^2)` 且 `n = V` 的情况，时间复杂度变为 `O(V^3)`。

## 方法 2 (高效)

由于给定的图是无向的，属于同一组件的所有顶点具有相同的可达节点集合。因此，我们跟踪顶点和组件的映射。图中的每个组件被分配一个数字，该组件中的每个顶点都被分配这个数字。我们使用 `visit` 数组来实现这一点，该数组用于在 `BFS` 中跟踪已访问的顶点。

```
对于一个节点 u，
如果 visit[u] 为 0 则
    u 之前未被访问过
否则 // 如果不为零则
   visit[u] 代表组件编号。

对于属于同一组件的任意两个节点 u 和 v，visit[u] 等于 visit[v]
```

要存储可达节点，请使用映射 `m`，其中键作为组件号，值作为向量，用于存储所有可达节点。

要找到节点 `u` 的可到达节点，请返回 `m[visit[u]]`。

查看下面的伪代码，以了解如何分配组件编号。

```
componentNum = 0
for i=1 to n
    If visit[i] is NOT 0 then
        componentNum++

// bfs() 返回给定顶点 'i' 的列表（或向量）
        list = bfs(i, componentNum)
        m[visit[i]] = list
```

对于示例中显示的图形，访问数组将是。

![VisitArray (2)](img/aca9d6f66af66522838c4b039b0860f8.png)

对于节点 1、2、3 和 4，组件号为 1。对于节点 5、6 和 7，组件号为 2。

以上想法的 C++ 实现

```cpp
// C++ program to find all the reachable nodes
// for every node present in arr[0..n-1].
#include <bits/stdc++.h>
using namespace std;

// This class represents a directed graph using
// adjacency list representation
class Graph
{
public:
    int V;    // No. of vertices

    // Pointer to an array containing adjacency lists
    list<int> *adj;

    Graph(int );  // Constructor

    void addEdge(int, int);

    vector<int> BFS(int, int, int []);
};

Graph::Graph(int V)
{
    this->V = V;
    adj = new list<int>[V+1];
}

void Graph::addEdge(int u, int v)
{
    adj[u].push_back(v); // Add w to v’s list.
    adj[v].push_back(u); // Add v to w’s list.
}

vector<int> Graph::BFS(int componentNum, int src,
                                    int visited[])
{
    // Mark all the vertices as not visited
    // Create a queue for BFS
    queue<int> queue;

    queue.push(src);

    // Assign Component Number
    visited[src] = componentNum;

    // Vector to store all the reachable nodes from 'src'
    vector<int> reachableNodes;

    while(!queue.empty())
    {
        // Dequeue a vertex from queue
        int u = queue.front();
        queue.pop();

        reachableNodes.push_back(u);

        // Get all adjacent vertices of the dequeued
        // vertex u. If a adjacent has not been visited,
        // then mark it visited nd enqueue it
        for (auto itr = adj[u].begin();
                itr != adj[u].end(); itr++)
        {
            if (!visited[*itr])
            {
                // Assign Component Number to all the
                // reachable nodes
                visited[*itr] = componentNum;
                queue.push(*itr);
            }
        }
    }
    return reachableNodes;
}

// Display all the Reachable Nodes from a node 'n'
void displayReachableNodes(int n,
            unordered_map <int, vector<int> > m)
{
    vector<int> temp = m[n];
    for (int i=0; i<temp.size(); i++)
        cout << temp[i] << " ";

    cout << endl;
}

// Find all the reachable nodes for every element
// in the arr
void findReachableNodes(Graph g, int arr[], int n)
{
    // Get the number of nodes in the graph
    int V = g.V;

    // Take a integer visited array and initialize
    // all the elements with 0
    int visited[V+1];
    memset(visited, 0, sizeof(visited));

    // Map to store list of reachable Nodes for a
    // given node.
    unordered_map <int, vector<int> > m;

    // Initialize component Number with 0
    int componentNum = 0;

    // For each node in arr[] find reachable
    // Nodes
    for (int i = 0 ; i < n ; i++)
    {
        int u = arr[i];

        // Visit all the nodes of the component
        if (!visited[u])
        {
            componentNum++;

            // Store the reachable Nodes corresponding to
            // the node 'i'
            m[visited[u]] = g.BFS(componentNum, u, visited);
        }

        // At this point, we have all reachable nodes
        // from u, print them by doing a look up in map m.
        cout << "Reachable Nodes from " << u <<" are\n";
        displayReachableNodes(visited[u], m);
    }
}

// Driver program to test above functions
int main()
{
    // Create a graph given in the above diagram
    int V = 7;
    Graph g(V);
    g.addEdge(1, 2);
    g.addEdge(2, 3);
    g.addEdge(3, 4);
    g.addEdge(3, 1);
    g.addEdge(5, 6);
    g.addEdge(5, 7);

    // For every ith element in the arr
    // find all reachable nodes from query[i]
    int arr[] = {2, 4, 5};

    // Find number of elements in Set
    int n = sizeof(arr)/sizeof(int);

    findReachableNodes(g, arr, n);

    return 0;
}
```

输出：

```
Reachable Nodes from 2 are
2 1 3 4
Reachable Nodes from 4 are
2 1 3 4
Reachable Nodes from 5 are
5 6 7
```

**时间复杂度分析**：

`n` = 给定集合的大小

`E` = 边数

`V` = 节点数

`BFS` 的 `O(V + E)`

在最坏的情况下，将为给定中存在的每个节点显示所有 `V` 节点，即图中仅一个组件，因此需要 `O(n * V)` 时间。

最坏情况下的时间复杂度：`O(V + E)` + `O(n * V)`

本文由 **Chirag Agarwal** 提供。 如果您喜欢 GeeksforGeeks 并希望做出贡献，则还可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 撰写文章，或将您的文章邮寄至 contribute@geeksforgeeks.org。 查看您的文章出现在 GeeksforGeeks 主页上，并帮助其他 Geeks。

如果发现任何不正确的地方，或者想分享有关上述主题的更多信息，请写评论。