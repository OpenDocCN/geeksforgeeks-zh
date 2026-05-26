# 如何在 Python 中给一个海底热图图添加一帧？

> 原文：[https://www.geeksforgeeks.org/how-to-add-a-frame-to-a-seaborn-heatmap-figure-in-python/](https://www.geeksforgeeks.org/how-to-add-a-frame-to-a-seaborn-heatmap-figure-in-python/)

热图是数据的图形表示，其中值用颜色表示。它们使复杂的数据一目了然。使用 Python 中的 `seaborn` 可以轻松绘制热图。在本文中，我们将为 Python 中的海底热图添加一个框架。

> 语法：`seaborn.heatmap(data, *vmin=None, vmax=None, cmap=None, center=None, annot_kws=None, linewidth=0, linecolor='white', cbar=True, **kwargs)`
>
> 重要参数：
> * `Data`：2D 数据集，可以强制转换为 `ndarray`。
> * `Line width`：每个单元格的线宽。
> * `Line color`：划分每个单元格的线条颜色。
> * `CBAR`：是否绘制颜色条。
>
> 除数据外的所有参数都是可选的。
>
> 返回：`matplotlib.axes._subplots.AxesSubplot` 类型的对象。

### 创建热图

为了绘制热图，我们将使用 `seaborn` 的内置数据集。`Seaborn` 有很多内置的数据集，比如 `titanic.csv`、`penguins.csv`、`flights.csv`、`exercise.csv`，我们也可以使用自己的数据集，它应该只是一个矩形数组。

## Python 3

```py
# Import libraries
import seaborn as sns
import matplotlib.pyplot as plt

# Preparing dataset
example = sns.load_dataset("flights")
example = example.pivot("month", "year",
                        "passengers")

# Creating plot
res = sns.heatmap(example)

# show plot
plt.show()
```