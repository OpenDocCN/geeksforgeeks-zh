# Python 中的 `Matplotlib.pyplot.subplot()` 函数

> 原文: [https://www.geeksforgeeks.org/matplotlib-pyplot-subplot-function-in-python/](https://www.geeksforgeeks.org/matplotlib-pyplot-subplot-function-in-python/)

**先决条件:** `matplotlib`

`subplot()` 函数将子图添加到指定网格位置的当前图形中。它类似于 `subplots()` 函数，但是不同于 `subplots()`，它一次添加一个子图。因此，要创建多个图，您需要几行带有 `subplot()` 函数的代码。`subplot()` 功能的另一个缺点是它删除了你图形上已经存在的绘图。请参考示例 1。

它是 `Figure.add_subplot` 的包装器。

**语法:**

> `subplot(nrows, ncols, index, **kwargs)`
>
> `subplot(pos, **kwargs)`
>
> `subplot(ax)`
>
> **参数:**
>
> *   **pos:** 描述子图位置的 3 位整数或三个独立的整数。
> *   **pos** 是一个三位数的整数，其中第一个、第二个和第三个整数是 `nrows`、`ncols` 和 `index`。
> *   **projection:** [{None, 'aitoff', 'hammer', 'lambert', 'mollweide', 'polar', 'rectilinear', 'str'}, 可选]。子图 (`axes`) 的投影类型。默认的 `None` 导致 `'rectilinear'` 投影。
> *   **label:** 【str】返回轴的标签。
> *   **kwargs:** 该方法还为返回的 `axes` 基类取关键字参数；除了图形参数，例如 `facecolor`。
>
> **返回:** 一个 `axes.Axes` 对象（或 `axes.Axes` 的子类）。返回的坐标轴基类取决于使用的投影。

该功能的实现如下:

## 例 1: `subplot()` 将删除预先存在的绘图

```py
# importing the module
import matplotlib.pyplot as plt

# Data to display on plot
x = [1, 2, 3, 4, 5]
y = [1, 2, 1, 2, 1]

# plot() will create new figure and will add axes object (plot) of above data
plt.plot(x, y, marker="x", color="green")

# subplot() will add plot to current figure deleting existing plot
plt.subplot(121)
```

**输出:** 我们可以看到第一个绘图被 `subplot()` 函数覆盖了。

![](img/f20db55aec977070267a0f2e42acd788.png)

`subplot_gfg`

如果你想看到第一个绘图，注释掉 `plt.subplot()` 行，你会看到下面的绘图。

![](img/39227b0dab4e1d3bce55c88fe8b70d8e.png)

`plot_gfg`

## 例 2:

```py
import matplotlib.pyplot as plt
# data to display on plots

x = [3, 1, 3]
y = [3, 2, 1]
z = [1, 3, 1]

# Creating figure object
plt.figure()

# adding first subplot
plt.subplot(121)
plt.plot(x, y, color="orange", marker="*")

# adding second subplot
plt.subplot(122)
plt.plot(z, y, color="yellow", marker="*")
```

**输出:**

![](img/e5ce77fb0aa41d7a438d831e3fc7e6ed.png)

`multiple_subplots`