# ML | 光学聚类解释

> 原文：[https://www.geeksforgeeks.org/ml-optics-clustering-explanation/](https://www.geeksforgeeks.org/ml-optics-clustering-explanation/)

**先决条件：** [DBSCAN聚类](https://www.geeksforgeeks.org/dbscan-clustering-in-ml-density-based-clustering/)

光学聚类代表**排序点以识别聚类结构**。它从 `DBSCAN` 聚类算法中得到启发。它为 `DBSCAN` 集群的概念增加了两个术语。它们是：

1.  **核心距离：** 它是将给定点分类为核心点所需的最小半径值。如果给定的点不是核心点，则其核心距离未定义。

![](img/f03148cd3d5ccadea2bf50248ee7f22b.png)

2.  **可达性距离：** 相对于另一个数据点 `q` 定义。点 `p` 和 `q` 之间的可达性距离是 `p` 的核心距离和 `p` 与 `q` 之间的欧几里德距离（或其他距离度量）的最大值。请注意，如果 `q` 不是核心点，则不定义可达性距离。

![](img/d1e487d9889911aff65e58fec3443c46.png)

这种聚类技术不同于其他聚类技术，因为这种技术没有明确地将数据分割成聚类。相反，它会生成可达性距离的可视化，并使用该可视化对数据进行聚类。

**伪代码：**

以下伪代码来自算法的[维基百科页面](https://en.wikipedia.org/wiki/OPTICS_algorithm)。

```python
OPTICS(DB, eps, MinPts)

#Repeating the process for all points in the database
    for each point pt of DB

#Initializing the reachability distance of the selected point
       pt.reachable_dist = UNDEFINED
    for each unprocessed point pt of DB

#Getting the neighbours of the selected point
       #according to the definitions of epsilon and
       #minPts in DBSCAN
       Nbrs = getNbrs(pt, eps)

mark pt as processed
       output pt to the ordered list

#Checking if the selected point is not noise
       if (core_dist(pt, eps, Minpts) != UNDEFINED)

#Initializing a priority queue to get the closest data point
          #in terms of Reachability distance
          Seeds = empty priority queue

#Calling the update function
          update(Nbrs, pt, Seeds, eps, Minpts)

#Repeating the process for the next closest point
          for each next q in Seeds
             Nbrs' = getNbrs(q, eps)
             mark q as processed
             output q to the ordered list
             if (core_dist(q, eps, Minpts) != UNDEFINED)
                update(Nbrs', q, Seeds, eps, Minpts)
```

更新函数的伪代码如下：

```python
update(Nbrs, pt, Seeds, eps, MinPts)

#Calculating the core distance for the given point
    coredist = core_dist(pt, eps, MinPts)

#Updating the Reachability distance for each neighbour of p
    for each obj in Nbrs
       if (obj is not processed)
          new_reach_distance = max(coredist, dist(pt, obj))

#Checking if the neighbour point is in seeds
          if (obj.reachable_dist == UNDEFINED)

#Updation step
              obj.reachabled_dist = new_reach_distance
              Seeds.insert(obj, new_reach_distance)
          else               
              if (new_reach_distance < obj.reachable_dist)

#Updation step
                 o.reachable_dist = new_reach_distance
                 Seeds.move-up(obj, new_reach_distance)
```

**光学聚类 v/s DBSCAN 聚类：**

1.  **内存成本：** `OPTICS` 群集技术需要更多内存，因为它维护一个优先级队列（最小堆）来确定下一个数据点，该数据点在可达性距离方面最接近当前正在处理的点。它还需要更多的计算能力，因为最近邻查询比 `DBSCAN` 中的半径查询更复杂。
2.  **更少的参数：** `OPTICS` 聚类技术不需要维护 `ε` 参数，仅在上述伪码中给出，以减少花费的时间。这导致参数调整的分析过程的减少。
3.  **非划分性：** 这种技术不会将给定的数据分成簇。它仅仅产生可达性距离图，并且根据程序员的解释相应地对点进行聚类。