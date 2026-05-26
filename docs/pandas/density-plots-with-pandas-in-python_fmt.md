# 密度图

> 原文: [https://www.geeksforgeeks.org/density-plots-with-pandas-in-python/](https://www.geeksforgeeks.org/density-plots-with-pandas-in-python/)

密度图是一种数据可视化工具。它是直方图的变体，在绘制值时使用“核平滑”。它是从数据推断出的直方图的连续平滑版本。

密度图使用核密度估计（因此也称为核密度估计图或 KDE），这是一种概率密度函数。峰值较高的绘图区域是那些值之间存在最大数据点的区域。

密度图可以用 `pandas`、`seaborn` 等来制作。在本文中，我们将使用 `pandas` 生成密度图。我们将使用 Seaborn 库的两个数据集，即 `'car_crashes'` 和 `'tips'`。

## 语法

`pandas.DataFrame.plot.density` 或 `pandas.DataFrame.plot.kde`

其中：
- `pandas` -> 为 `pandas.DataFrame` 类型的数据集
- `DataFrame` -> 为其绘制密度图的列
- `plot` -> 关键词指导绘制给定列的图/图形
- `density` -> 用于绘制密度图
- `kde` -> 使用核密度估计函数绘制密度图

## 示例 1

给定数据集 `'car_crashes'`，让我们使用密度图找出大多数车祸发生的最常见速度。

```py
# importing the libraries
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# loading the dataset
# from seaborn library
data = sns.load_dataset('car_crashes')

# viewing the dataset
print(data.head(4))
```