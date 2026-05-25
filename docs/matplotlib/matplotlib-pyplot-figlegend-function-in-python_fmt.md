# Matplotlib 中的 `pyplot.figlegend()` 函数

> 原文: [https://www.geeksforgeeks.org/matplotlib-pyplot-figlegend-function-in-python/](https://www.geeksforgeeks.org/matplotlib-pyplot-figlegend-function-in-python/)

Matplotlib 是一个 Python 库，用于使用 Pyplot 创建、动画和编辑图形、绘图和图形。`matplotlib.pyplot` 根据用户需求的偏好和需求，定义了许多功能供用户使用。

## `matplotlib.pyplot.figlegend()`

这是用来在图形上放置图例的。Matplotlib 中的图例类似于定义图中曲线的铭牌。

> **语法:** `matplotlib.pyplot.figlegend(*args, **kwargs)`
> **参数:** 一些重要参数有:
> 
> *   `handles`: 所有图形线条（或技术术语中的艺术家）列表。要添加到图例中的艺术家（线条、面片）列表将作为不同的句柄。在 `figlegend()` 中，指定句柄是可选的。
> *   `labels`: 图例的实际名称列表。显示艺术家实际价值的标签列表称为标签。在 `figlegend()` 中，指定标签是可选的，如果未指定标签，则 `figlegend()` 函数会将其命名为图例 1、图例 2 等。
> *   `loc`: 图例的位置（默认: "best"）。
> 
> **返回:** 返回要放在图上的图例。

**示例 1:** 创建了值为 `x = [0, 0.1, 0.2, ..., 5]` 和 `y = sin(x)` 的数据集，然后使用 `label="Sin"` 绘制 x 轴为数据集 `x`、y 轴为数据集 `y` 的图形，并使用之前指定的标签作为图例，使用默认的 `figlegend()` 绘制图形。

```py
# Importing the necessary modules
import numpy as np
import matplotlib.pyplot as plt

# Creating a dataset
x = np.arange(0, 5, 0.1)
y = np.sin(x)

# Plotting the data
plt.plot(x, y, label = "Sin")

# Legend
plt.figlegend()
```

**输出:**

![figlegend()](img/4ccd4f25f958c750270c1ed7e96bd181.png)

**示例 2:** 使用与上面相同的方法，但显示了 `figlegend()` 句柄和标签的使用，但使用了默认位置。

```py
# Importing the necessary modules
import numpy as np
import matplotlib.pyplot as plt

# Creating a dataset
x = np.arange(0, 5, 0.1)
y = np.cos(x)

# Plotting the data
line1 = plt.plot(x, y)

# Legend
plt.figlegend((line1),('Cos'))
```

**输出:**

![figlegend plot-2](img/0c3779c4d8b996ef256313ca47092aba.png)

**示例 3:** 通过在 `tan` 和 `cos` 函数的一个图上绘制两个图形，展示了 `figlegend(handles, labels, loc)` 函数的使用。

```py
# Importing the necessary modules
import numpy as np
import matplotlib.pyplot as plt

# Creating a dataset
x = np.arange(0, 5, 0.1)
y = np.tan(x)

x1 = np.arange(0, 5, 0.1)
y1 = np.cos(x)

# Plotting the data
line1 = plt.plot(x, y)
line2 = plt.plot(x1, y1)

# Legend
plt.figlegend(
    handles = (line1, line2),
    labels = ("Tan", "Cos"),
    loc='upper right'
)
```

**输出:**

![figlegend plot-3](img/0a17ed5b6d4ff0712e25ff5ec05e9cc1.png)