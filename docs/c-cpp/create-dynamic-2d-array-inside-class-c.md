# 如何用 C++ 在类内部创建动态 2D 数组？

> 原文:[https://www . geesforgeks . org/create-dynamic-2d-array-class 内-c/](https://www.geeksforgeeks.org/create-dynamic-2d-array-inside-class-c/)

假设我们想为 Graph 创建一个类。该类存储图的邻接矩阵表示。因此，我们的类结构如下所示。

```cpp
class Graph 
{
  int V; 
  int adj[V][V];  // This line doesn't work

  /* Rest of the members */
};

int main()
{
}
```

输出:

```cpp
error: invalid use of non-static data
       member 'Graph::V'.

```

即使我们将 V 设为静态，我们也会得到错误“数组边界不是整数常数”

C++ 不允许在大小不恒定的类中创建堆栈分配数组。所以我们需要动态分配内存。下面是一个简单的程序，展示了如何使用带有邻接矩阵表示的 Graph 类在 C++ 类中动态分配 2D 数组。

```cpp
// C++ program to show how to allocate dynamic 2D
// array in a class using a Graph example.
#include<bits/stdc++.h>
using namespace std;

// A Class to represent directed graph
class Graph
{
    int V;    // No. of vertices

    // adj[u][v] would be true if there is an edge
    // from u to v, else false
    bool **adj;

public:
    Graph(int V);   // Constructor

    // function to add an edge to graph
    void addEdge(int u, int v)  { adj[u][v] = true; }
    void print();
};

Graph::Graph(int V)
{
    this->V = V;

    // Create a dynamic array of pointers
    adj = new bool* [V];

    // Create a row for every pointer
    for (int i=0; i<V; i++)
    {
       // Note : Rows may not be contiguous
       adj[i] = new bool[V];

       // Initialize all entries as false to indicate
       // that there are no edges initially
       memset(adj[i], false, V*sizeof(bool));
    }
}

// Utility method to print adjacency matrix
void Graph::print()
{
   for (int u=0; u<V; u++)
   {
      for (int v=0; v<V; v++)
         cout << adj[u][v] << " ";
      cout << endl;
   }
}

// Driver method
int main()
{
    // Create a graph given in the above diagram
    Graph g(4);
    g.addEdge(0, 1);
    g.addEdge(0, 2);
    g.addEdge(1, 2);
    g.addEdge(2, 0);
    g.addEdge(2, 3);
    g.addEdge(3, 3);

    g.print();

    return 0;
}
```

输出:

```cpp
0 1 1 0 
0 0 1 0 
1 0 0 1 
0 0 0 1 

```

**memset()的调用说明:**
memset()单独用于各行。我们不能用一个调用来代替这些调用，因为行被分配在不同的地址，进行如下的 memset 调用将是灾难性的。

```cpp
       // Wrong!! (Rows of matrix at different addresses)
       memset(adj, false, V*V*sizeof(bool));
```

本文由 **Dheeraj Gupta** 供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论