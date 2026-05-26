# Pandas DataFrame.hist()函数

> 原文: [https://www.geeksforgeeks.org/pandas-dataframe-hist-function-in-python/](https://www.geeksforgeeks.org/pandas-dataframe-hist-function-in-python/)

`DataFrame.hist()` 函数对于理解数值变量的分布很有用。该函数将值分解成数值变量。它的主要功能是制作给定数据帧的直方图。

数据的分布由**直方图**表示。当使用函数 `Pandas DataFrame.hist()` 时，它会自动调用 `DataFrame` 中每个系列的函数 `matplotlib.pyplot.hist()`。结果，我们获得了每列一个直方图。

## 语法

`DataFrame.hist(data, column=None, by=None, grid=True, xlabelsize=None, xrot=None, ylabelsize=None, yrot=None, ax=None, sharex=False, sharey=False, figsize=None, layout=None, bins=10, backend=None, legend=False, **kwargs)`

## 参数

- `data` : `DataFrame`
- `column` : `str` 或 `sequence`
- `xlabelsize` : `int`, 默认 `None`
- `ylabelsize` : `int`, 默认 `None`
- `ax` : `Matplotlib axes object`, 默认 `None`
- `**kwargs`
  所有其他绘图关键字参数都要传递给 `matplotlib.pyplot.hist()`。

## 返回

`matplotlib.axes.AxesSubplot` 或 `numpy.ndarray`

## 示例1: 创建Pandas数据帧的2列的直方图

有时我们需要绘制数据框各列的直方图，以便更深入地分析它们。在这种情况下，`dataframe.hist()` 函数帮助很大。使用这个函数，我们可以绘制任意多列的直方图。

```py
# Importing pandas library
import pandas as pd

# Creating a Data frame
values = pd.DataFrame({
    'Length': [2.7, 8.7, 3.4, 2.4, 1.9],
    'Breadth': [4.24, 2.67, 7.6, 7.1, 4.9]
})

# Creating Histograms of columns 'Length'
# and 'Breadth' using Dataframe.hist()
# function
hist = values.hist(bins=5)
```

**输出:**

![](img/959c6b845ba84ca94b884c16c13e2d51.png)

在上例中，我们使用 `dataframe.hist()` 函数绘制了列 `Length` 和列 `Breadth` 的直方图。

## 示例2: 创建Pandas数据帧的3列的直方图

```py
# Importing pandas library
import pandas as pd

# Creating a Data frame
values = pd.DataFrame({
    'Length': [2.7, 8.7, 3.4, 2.4, 1.9],
    'Breadth': [4.24, 2.67, 7.6, 7.1, 4.9],
    'Height': [5.8, 5.5, 7.8, 10.88, 0.1]})

# Creating Histograms of columns 'Length',
# 'Breadth' and 'Height' using Dataframe.hist()
# function
hist = values.hist(bins=12)
```

**输出:**

![](img/0c9882d2f92a442e2c97cef8b648ccf9.png)

在上例中，我们使用 `dataframe.hist()` 函数绘制了 `Length`、`Breadth` 和 `Height` 列的直方图。

## 示例3: 创建Pandas数据帧的4列的直方图

```py
# Importing pandas library
import pandas as pd

# Creating a Data frame
values = pd.DataFrame({
    'Length': [2.7, 8.7, 3.4, 2.4, 1.9],
    'Breadth': [4.24, 2.67, 7.6, 7.1, 4.9],
    'Height': [5.8, 5.5, 7.8, 10.88, 0.1],
    'Weight': [20, 40.8, 55.8, 7.2, 48]
})

# Creating Histograms of columns 'Length',
# 'Breadth', 'Height' and 'Weight'
# using Dataframe.hist() function
hist = values.hist(bins=8)
```

**输出:**

![](img/76b924b778b89f5bd81e792cc27fa55e.png)

在上例中，我们使用 `dataframe.hist()` 函数绘制了列 `Length`、`Breadth`、`Height` 和 `Weight` 的直方图。