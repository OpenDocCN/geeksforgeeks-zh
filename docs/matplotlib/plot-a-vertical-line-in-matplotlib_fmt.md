# 在 Matplotlib 中绘制垂直线

> 原文: [https://www.geeksforgeeks.org/plot-a-vertical-line-in-matplotlib/](https://www.geeksforgeeks.org/plot-a-vertical-line-in-matplotlib/)

Matplotlib 是一个流行的用于绘图的 Python 库，它提供了一个面向对象的应用编程接口来渲染图形用户界面图。画一条水平线相当简单，下面的代码展示了如何做到这一点。

## 做一条垂直线

### 方法#1: 使用 `axvline()`

此功能添加穿过绘图轴的垂直线。

> **语法**: `matplotlib.pyplot.axvline(x, color, xmin, xmax, linestyle)`
>
> **参数:**
>
> *   `x`: 在 X 轴上的位置绘制直线，它接受整数。
> *   `xmin` 和 `xmax`: 标量，可选，默认:0/1。它绘制给定范围内的直线。
> *   `color`: 线条的颜色，它接受一个字符串。例如“r”或“b”。
> *   `linestyle`: 指定线型，它接受字符串。例如“-”、“--”、“-.”、':'、'None'、' '、""、'solid'、'dashed'、'dashdot'、'dotted'。

```py
# importing the modules
import matplotlib.pyplot as plt
import numpy as np

# specifying the plot size
plt.figure(figsize = (10, 5))

# only one line may be specified; full height
plt.axvline(x = 7, color = 'b', label = 'axvline - full height')

# rendering plot
plt.show()
```

**输出:**

![](img/545a21cf2f15a20765cb78196dca5307.png)

### 方法 2: 使用 `vlines()`

`matplotlib.pyplot.vlines()` 是用于绘制数据集的函数。在 `matplotlib.pyplot.vlines()` 中，vline 是垂直线的缩写。这个函数的作用从展开的形式中非常清楚，它表示这个函数处理的是穿过轴的垂直线的绘制。

> **语法**: `vlines(x, ymin, ymax, color, linestyle)`
>
> **参数:**
>
> *   `x`: 在 X 轴上的位置绘制直线，它接受整数。
> *   `ymin` 和 `ymax`: 标量，可选，默认:0/1。它绘制给定范围内的直线。
> *   `color`: 线条的颜色，它接受一个字符串。例如“r”或“b”。
> *   `linestyle`: 指定线型，它接受字符串。例如“-”、“--”、“-.”、':'、'None'、' '、""、'solid'、'dashed'、'dashdot'、'dotted'。

```py
# importing necessary libraries
import matplotlib.pyplot as plt
import numpy as np

# defining an array
xs = [1, 100]

# defining plot size
plt.figure(figsize = (10, 7))

# single line
plt.vlines(x = 37, ymin = 0, ymax = max(xs),
           colors = 'purple',
           label = 'vline_multiple - full height')

plt.show()
```

**输出:**

![](img/42206eeb82cbd5feffd5771beadd3d15.png)

### 方法三: 使用 `plot()`

Matplotlib 库 pyplot 模块中的 `plot()` 函数用于绘制 x，y 点的 2D 六边形宁滨图。

> **语法:** `plot(x_points, y_points, scalex=False)`
>
> **参数:**
>
> *   `x_points`/`y_points`: 点绘图。
> *   `scalex`/`scaley`: Bool，这些参数决定视图限制是否适应数据限制。

```py
# importing library
import matplotlib.pyplot as plt

# defining plot size
plt.figure(figsize = (10, 5))

# specifying plot coordinates
plt.plot((0, 0), (0, 1), scaley = False)

# setting scaley = True will make the line fit
# withn the frame, i.e It will appear as a finite line
plt.show()
```

**输出:**

![](img/c12ec7ec5669c41ab08e17aa2c082b92.png)

## 用图例绘制多条线

以下方法可用于在 Python 中绘制多条线。

### 方法#1: 使用 `axvline()`

```py
# importing the modules
import matplotlib.pyplot as plt
import numpy as np

# specifying the plot size
plt.figure(figsize = (10, 5))

# only one line may be specified; full height
plt.axvline(x = 7, color = 'b', label = 'axvline - full height')

# only one line may be specified; ymin & ymax specified as
# a percentage of y-range
plt.axvline(x = 7.25, ymin = 0.1, ymax = 0.90, color = 'r',
            label = 'axvline - % of full height')

# place legend outside
plt.legend(bbox_to_anchor = (1.0, 1), loc = 'upper left')

# rendering plot
plt.show()
```

**输出:**

![](img/0ea32abae1680a5d2d5b1ae1325ac4d9.png)

### 方法 2: 使用 `vlines()`

```py
# importing necessary libraries
import matplotlib.pyplot as plt
import numpy as np

# defining an array
xs = [1, 100]

# defining plot size
plt.figure(figsize = (10, 7))

# multiple lines all full height
plt.vlines(x = [37, 37.25, 37.5], ymin = 0, ymax = max(xs),
           colors = 'purple',
           label = 'vline_multiple - full height')

# multiple lines with varying ymin and ymax
plt.vlines(x = [38, 38.25, 38.5], ymin = [0, 25, 75], ymax = max(xs),
           colors = 'teal',
           label = 'vline_multiple - partial height')

# single vline with full ymin and ymax
plt.vlines(x = 39, ymin = 0, ymax = max(xs), colors = 'green',
           label = 'vline_single - full height')

# single vline with specific ymin and ymax
plt.vlines(x = 39.25, ymin = 25, ymax = max(xs), colors = 'green',
           label = 'vline_single - partial height')

# place legend outside
plt.legend(bbox_to_anchor = (1.0, 1), loc = 'upper left')
plt.show()
```

**输出:**

![](img/1d98b9d19f277f784598e7755e48015c.png)