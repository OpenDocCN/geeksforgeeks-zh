# 如何在 Matplotlib 中将图例放置在图表之外？

> 原文：[https://www.geeksforgeeks.org/how-to-place-legend-outside-of-the-plot-in-matplotlib/](https://www.geeksforgeeks.org/how-to-place-legend-outside-of-the-plot-in-matplotlib/)

在本文中，我们将看到如何在 Matplotlib 中将图例放置在图表之外？我们来讨论一些概念：

*   **Matplotlib**：Matplotlib 是 Python 中一个出色的可视化库，用于创建数组的二维图表。它是一个多平台的数据可视化库，构建在 NumPy 数组之上，并设计为与更广泛的 SciPy 堆栈协同工作。它由 John Hunter 于 2002 年推出。
*   **Legend**：图例是一个描述图形元素的区域。在 Matplotlib 库中，有一个名为 `legend()` 的函数用于在坐标轴上放置图例。`legend()` 中的 `loc` 属性用于指定图例的位置。`loc` 的默认值是 `loc='best'`（左上角）。

**在这里，首先我们来看看为什么需要在图表外部放置图例。**

## Python 3

```py
# importing packages
import numpy as np
import matplotlib.pyplot as plt

# create data
x=np.linspace(-20, 20, 1000)

# plot the graphs
plt.plot(x,np.sin(x))
plt.plot(x,np.cos(x))

# add legends
plt.legend(["Sine","Cosine"])

plt.show()
```