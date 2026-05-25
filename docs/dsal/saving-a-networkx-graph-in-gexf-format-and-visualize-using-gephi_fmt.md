# 保存 GEXF 格式的网络图，并使用 Gephi 可视化

> 原文: [https://www.geeksforgeeks.org/saving-a-networkx-graph-in-gexf-format-and-visualize-using-gephi/](https://www.geeksforgeeks.org/saving-a-networkx-graph-in-gexf-format-and-visualize-using-gephi/)

**先决条件:** [NetworkX](https://www.geeksforgeeks.org/networkx-python-software-package-study-complex-networks/)

NetworkX 是一个 Python 语言软件包，用于创建、操作和研究复杂网络的结构、动力学和功能。它被用来研究以具有节点和边的图的形式表示的大型复杂网络。使用 `networkx`，我们可以加载和存储复杂的网络。我们可以生成许多类型的随机和经典网络，分析网络结构，建立网络模型，设计新的网络算法和绘制网络。

在本文中，我们将讨论如何以 GEXF 格式保存网络图，然后使用 Gephi 将其可视化。

**GEXF** 代表**图形交换 XML 格式。** 虽然它有支持图形可视化的特性，但是 NetworkX 库提供的可视化方法有一定的局限性。因此，需要使用外部工具，如用于图形可视化的 Gephi。但是我们不能直接将图从 Python 导出到 Gephi，我们需要将图转换成它支持的格式。GEXF 就是这样一种文件格式。

需要先安装 Gephi 才能使用: [Gephi](https://gephi.org/)

## 以 GEXF 格式保存网络图

为了实现这一点，我们将使用 `write_gexf()` 函数，顾名思义，该函数可以轻松地将网络图保存为 GEXF 格式。

> **语法:**
>
> `NetworkX.write_gexf(G, path)`
>
> **参数:**
>
> *   `G`: 在此参数中，NetworkX 图对象（简称图）作为参数传入。
> *   `path`: 在此参数中，指定保存图形的有效路径。

**方法:**

*   导入模块
*   创建一个网络图
*   将此图保存为 GEXF 格式。

**程序:**

### Python 3

```python
# importing the required module
import networkx as nx

# making a simple graph with 1 node.
G = nx.path_graph(10)

# saving graph created above in gexf format
nx.write_gexf(G, "geeksforgeeks.gexf")
```