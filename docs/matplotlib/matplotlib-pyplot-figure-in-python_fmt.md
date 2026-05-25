# matplotlib.pyplot.figure() 函数详解

> 原文链接: [https://www.geeksforgeeks.org/matplotlib-pyplot-figure-in-python/](https://www.geeksforgeeks.org/matplotlib-pyplot-figure-in-python/)

**[Matplotlib](https://www.geeksforgeeks.org/python-introduction-matplotlib/)** 是 Python 中的一个库，是 NumPy 库的数值-数学扩展。**[Pyplot](https://www.geeksforgeeks.org/pyplot-in-matplotlib/)** 是一个基于状态的接口到 **Matplotlib** 模块，它提供了一个类似于 MATLAB 的接口。Pyplot 中可以使用的各种图有线图、等高线图、直方图、散点图、三维图等。

## 函数介绍

`matplotlib` 库 `pyplot` 模块中的 `figure()` 函数用于创建新图形。

### 语法

```python
matplotlib.pyplot.figure(num=None, figsize=None, dpi=None, facecolor=None, edgecolor=None, frameon=True, FigureClass=<class 'matplotlib.figure.Figure'>, clear=False, **kwargs)
```

### 参数

该方法接受以下描述的参数:

*   `num`: 提供了此参数，并且已经存在一个具有此 id 的图形。
*   `figsize (float, float)`: 这些参数是以英寸为单位的宽度和高度。
*   `dpi`: 该参数为图的分辨率。
*   `facecolor`: 该参数为背景颜色。
*   `edgecolor`: 该参数为边框颜色。
*   `frameon`: 此参数抑制绘制图形框架。
*   `FigureClass`: 该参数使用自定义图形实例。
*   `clear`: 此参数如果为真且图形已经存在，则清除。

### 返回值

该方法返回以下值:

*   `Figure`: 这将返回返回的图实例也将被传递给后端的 `new_figure_manager`。

## 示例

下面的例子说明了 `matplotlib.pyplot.figure()` 函数在 `matplotlib.axes` 中的作用:

### 示例 1

```python
# Implementation of matplotlib function
import matplotlib.pyplot as plt
import matplotlib.lines as lines

fig = plt.figure()
fig.add_artist(lines.Line2D([0, 1, 0.5], [0, 1, 0.3]))
fig.add_artist(lines.Line2D([0, 1, 0.5], [1, 0, 0.2]))

plt.title('matplotlib.pyplot.figure() Example\n',
                fontsize = 14, fontweight ='bold')

plt.show()
```

**输出:**
![](img/58988fe82def10635ee994da160f3e0a.png)

### 示例 2

```python
# Implementation of matplotlib function
import matplotlib.pyplot as plt
from mpl_toolkits.axisartist.axislines import Subplot

fig = plt.figure(figsize =(4, 4))

ax = Subplot(fig, 111)
fig.add_subplot(ax)

ax.axis["left"].set_visible(False)
ax.axis["bottom"].set_visible(False)

plt.title('matplotlib.pyplot.figure() Example\n', 
                fontsize = 14, fontweight ='bold')

plt.show()
```

**输出:**
![](img/8c378910d4906462608469a2841de2b0.png)