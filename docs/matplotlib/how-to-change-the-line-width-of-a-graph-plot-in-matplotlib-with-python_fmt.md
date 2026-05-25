# 如何用 Python 在 Matplotlib 中更改图形绘制的线宽？

> 原文：[https://www.geeksforgeeks.org/how-to-change-the-line-width-of-a-graph-plot-in-matplotlib-with-python/](https://www.geeksforgeeks.org/how-to-change-the-line-width-of-a-graph-plot-in-matplotlib-with-python/)

**先决条件**：[Matplotlib 入门](https://www.geeksforgeeks.org/python-introduction-matplotlib/)

在本文中，我们将学习如何用 Python 在 Matplotlib 中更改图形绘制的线宽。为此，必须熟悉以下概念：

*   [**Matplotlib**](https://www.geeksforgeeks.org/python-introduction-matplotlib/)：Matplotlib 是一个强大的 Python 可视化库，用于创建数组的 2D 图形。它是一个跨平台的数据可视化库，构建在 NumPy 数组之上，旨在与更广泛的 SciPy 堆栈协同工作。它由 John Hunter 于 2002 年推出。
*   [**曲线图**](https://www.geeksforgeeks.org/graph-plotting-in-python-set-1/)：曲线图是一种表示数据集的图形技术，通常以曲线形式显示两个或多个变量之间的关系。
*   **线宽**：线的宽度称为线宽。在 Matplotlib 中，可以使用一个属性来改变图形的线宽。

## 方法

*   导入包。
*   导入或创建数据。
*   用线绘制曲线图。
*   使用 `linewidth` 属性设置线宽（`lw` 也可用作简写形式）。

### 示例 1

```python
# importing packages
import matplotlib.pyplot as plt
import numpy as np

# create data
x_values = np.arange(0, 10)
y_values = np.arange(0, 10)

# Adjust the line widths
plt.plot(x_values, y_values - 2, linewidth=5)
plt.plot(x_values, y_values)
plt.plot(x_values, y_values + 2, lw=5)

# add legends and show
plt.legend(['Lw = 5', 'Lw = auto', 'Lw = 5'])
plt.show()
```

**输出：**

![](img/224531ae73aa83594998129ce789c51c.png)

### 示例 2

```python
# importing packages
import matplotlib.pyplot as plt
import numpy as np

# create data
x_values = np.linspace(0, 10, 1000)
y_values = np.sin(x_values)

# Adjust the line widths
for i in range(20):
    plt.plot(x_values, y_values + i*0.5, lw=i*0.5)

plt.show()
```

**输出：**

![](img/c1aa0fb0bbe6d16d9f1c9337d8c09ca3.png)

### 示例 3

```python
# importing packages
import matplotlib.pyplot as plt
import numpy as np

# create data
x_values = np.linspace(0, 10, 1000)

# Adjust the line widths
for i in range(20):
    plt.plot(x_values, np.sin(x_values) + i*0.5, lw=i*0.4)
    plt.plot(x_values, np.cos(x_values) + i*0.5, lw=i*0.4)

plt.show()
```

**输出：**

![](img/6e76b65472fd226c2fe3c48cf7d47983.png)