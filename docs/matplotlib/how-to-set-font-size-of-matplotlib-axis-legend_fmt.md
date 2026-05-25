# 如何设置 Matplotlib 轴图例的字体大小？

> 原文：[https://www.geeksforgeeks.org/how-to-set-font-size-of-matplotlib-axis-legend/](https://www.geeksforgeeks.org/how-to-set-font-size-of-matplotlib-axis-legend/)

**先决条件：** Matplotlib

在本文中，我们将看到如何使用 Python 设置 matplotlib 轴图例的字体大小。为此，我们将使用 `rcParams()` 方法来增加/减少字体大小。为此，我们必须重写 `matplotlib.rcParams['legend.fontsize']` 方法。

> **语法：** `matplotlib.rcParams['legend.fontsize'] = font_size_value`

### 示例 1：将图例的字体大小设置为 15

```py
# import required modules
import numpy
from matplotlib import pyplot
import matplotlib

# assign value to x axis
x_axis = numpy.arange(1, 20, 0.5)

# get the value of log10
y_axis_log10 = numpy.exp(x_axis)

# plot the graph
pyplot.plot(x_axis, y_axis_log10, c="blue",
            label="exponential")

# title of the graph/plot
pyplot.title("Exponential Graph Plot")

# to set the font size of the legend
matplotlib.rcParams['legend.fontsize'] = 15

pyplot.legend(loc='best')

pyplot.show()
```

**输出：**

![](img/7b35a4a8e41d7a132d6c61b83ba96af7.png)

### 示例 2：将图例的字体大小设置为 25

```py
# import required modules
import numpy
from matplotlib import pyplot
import matplotlib

# assign value to x axis
x_axis = numpy.arange(1, 20, 0.5)

# get the value of log10
y_axis_log10 = numpy.exp(x_axis)

# plot the graph
pyplot.plot(x_axis, y_axis_log10, c="blue", label="exponential")

# Title of the graph/ploy
pyplot.title("Exponential Graph Plot")

# to set the font size of the legend
matplotlib.rcParams['legend.fontsize'] = 25

pyplot.legend(loc='best')

pyplot.show()
```

**输出：**

![](img/a6ede5cf8890d1052fd012233fbcdb24.png)