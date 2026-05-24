# 迪杰斯特拉算法和弗洛伊德-沃肖尔算法的比较

> 原文:[https://www . geeksforgeeks . org/comparison-dijkstras-Floyd-war shall-algorithms/](https://www.geeksforgeeks.org/comparison-dijkstras-floyd-warshall-algorithms/)

## 主要目的

*   [`Dykstra algorithm`](https://www.geeksforgeeks.org/greedy-algorithms-set-6-dijkstras-shortest-path-algorithm/) 是单源最短路径（SSSP）算法的一个例子，即给定一个源顶点，它找到从源到所有其他顶点的最短路径。
*   [`Freud Washer's algorithm`](https://www.geeksforgeeks.org/dynamic-programming-set-16-floyd-warshall-algorithm/) 是全对最短路径算法的一个例子，这意味着它计算所有节点对之间的最短路径。

## 时间复杂度

*   `Dykstra`算法的时间复杂度：`O(E log V)`
*   `Freud Washer`的时间复杂度：`O(V^3)`

## 其他点

*   我们可以通过在每个顶点上运行`Dijskstra`的最短路径算法来找到所有对的最短路径。但这种方法的时间复杂度是`O(VE Log V)`，在最坏情况下可能达到`O(V^3 logV)`。
*   算法之间的另一个重要区别是它们对分布式系统的适用性。与`Dijkstra`算法不同，`Floyd Warshall`可以在分布式系统中实现，这使其适用于像图的图（`Graph of Graphs`）这样的数据结构。
*   最后，`Freud Washer`适用于负权重边，但不能检测[负环](https://www.geeksforgeeks.org/detect-negative-cycle-graph-bellman-ford/)，而`Dykstra`算法不适用于负权重边。

本文由**vinet Joshi**供稿。如果你喜欢`GeeksforGeeks`并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到`contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。