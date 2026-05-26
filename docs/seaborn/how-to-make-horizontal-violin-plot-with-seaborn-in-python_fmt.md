# 如何用 Python 制作水平小提琴图与 Seaborn？

> 原文：[https://www.geeksforgeeks.org/how-to-make-horizontal-violin-plot-with-seaborn-in-python/](https://www.geeksforgeeks.org/how-to-make-horizontal-violin-plot-with-seaborn-in-python/)

在这篇文章中，我们将学习如何使用 `seaborn` 绘制一个水平的小提琴图。我们可以使用两种方法绘制水平小提琴图：`violinplot()` 和 `violinplot()`。

## 方法 1：使用 `violinplot()`

一个小提琴图扮演着与箱线图或须线图类似的角色，因为它显示了一个或多个分类变量的若干定量数据。在多个单元格中显示多个数据可能是一种有效且有吸引力的方式。“宽格式”数据框有助于维护可以在图表上绘制的每个数字列。可以使用 NumPy 或 Python 对象，但 Pandas 对象更好，因为相关名称将用于注释轴。

> **语法：** `seaborn.violinplot(x=None, y=None, hue=None, data=None, scale_hue=True, **kwargs)`
>
> **参数：**
> `x, y, hue`：用于绘制长格式数据的输入。
> `data`：用于绘图的数据集。
> `scale`：用来缩放每把小提琴宽度的方法。
>
> **返回：** 该方法返回绘制了绘图的坐标轴对象。

### 示例 1：仅使用一个轴绘制单个水平图

如果我们只使用一个数据变量，而不是两个数据变量，那么这意味着轴将这些数据变量表示为一个轴。

`x` 表示 x 轴，`y` 表示 y 轴。

**语法：**

```py
seaborn.violinplot(x)
```

## Python 3 示例

```py
# Python program to illustrate
# violinplot using inbuilt data-set
# given in seaborn

# importing the required module
import seaborn

# use to set style of background of plot
seaborn.set(style="whitegrid")

# loading data-set
tips = seaborn.load_dataset("tips")

seaborn.violinplot(x=tips["total_bill"])
```