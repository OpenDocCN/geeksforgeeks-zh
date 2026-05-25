# Python中的matplotlib.patches.ConnectionPatch类

> 原文：[https://www.geeksforgeeks.org/matplotlib-patches-connectionpatch-class-in-python/](https://www.geeksforgeeks.org/matplotlib-patches-connectionpatch-class-in-python/)

[**Matplotlib**](https://www.geeksforgeeks.org/python-matplotlib-an-overview/) 是Python中一个惊人的可视化库，用于数组的2D图。Matplotlib绘图库是一个基于NumPy阵列的多平台数据可视化库，旨在与更广泛的SciPy堆栈协同工作。

## matplotlib.patches.ConnectionPatch

`matplotlib.patches.ConnectionPatch`是`matplotlib.patches.FancyArrowPatch`类的一个子类，用于在两点之间建立连接线。

> **语法：**
> `class matplotlib.patches.ConnectionPatch(xyA, xyB, coordsA, coordsB=None, axesA=None, axesB=None, arrowstyle='-', arrow_transmuter=None, connectionstyle='arc3', connector=None, patchA=None, patchB=None, shrinkA=0.0, shrinkB=0.0, mutation_scale=10.0, mutation_aspect=None, clip_on=False, dpi_cor=1.0, **kwargs)`
>
> **参数：**
>
> *   `xyA`：是x-y图上连线的起点，也叫A点。
> *   `xyB`：是x-y图上连线的起点，也叫B点。
> *   `coordsA`：点A的坐标。
> *   `coordsB`：点B的坐标。
> *   `axesA`：是x-y图上连接轴的起点。
> *   `axesB`：是x-y图上连接轴的终点。
> *   `arrowstyle`：用于连接箭头的样式。它的默认类型是`'-'`。
> *   `arrow_transmuter`：用来忽略一条连接线。
> *   `connectionstyle`：描述了`xyA`和`xyB`是如何连接的。它可以是类`ConnectionStyle`的实例，也可以是名为`connectionstyle`的字符串，它有可选的逗号分隔属性。
> *   `connector`：一般被忽略，决定忽略哪个连接器。
> *   `patchA`：用于在A点添加面片。
> *   `patchB`：用于在B点添加面片。
> *   `shrinkA`：用于收缩A点的连接器。
> *   `shrinkB`：用于收缩B点的连接器。
> *   `mutation_scale`：箭头样式属性（如`head_length`）缩放的值。
> *   `mutation_aspect`：突变前矩形的高度会被这个值挤压，突变后的盒子会被它的倒数拉伸。
> *   `clip_on`：设置艺术家是否使用剪辑。
> *   `dpi_cor`：`dpi_cor`目前用于线宽相关的东西和收缩因子。突变规模受此影响。

以下是有效Kwargs密钥列表：

| 键 | 描述 |
| --- | --- |
| `arrowstyle` | 箭头样式 |
| `connectionstyle` | 连接方式 |
| `repo` | 默认值为`(0.5, 0.5)` |
| `patchA` | 默认为文本的边框 |
| `patchB` | 默认为无 |
| `shrinkA` | 默认值为2点 |
| `shrinkB` | 默认值为2点 |
| `mutation_scale` | 默认为文本大小（以磅为单位） |
| `mutation_aspect` | 默认值为1。 |
| `?` | `matplotlib.patches.Patch`的任意键 |

`xyA`和`xyB`的坐标由字符串`coordsA`和`coordsB`表示。

| 属性 | 描述 |
| --- | --- |
| `'figure points'` | 图左下角的点 |
| `'figure pixels'` | 图左下角的像素 |
| `'figure fraction'` | 0,0是图的左下角，1,1是右上角 |
| `'axes points'` | 轴左下角的点 |
| `'axes pixels'` | 轴左下角的像素 |
| `'axes fraction'` | 0,0是轴的左下方，1,1是右上方 |
| `'data'` | 使用被注释对象的坐标系（默认） |
| `'offset points'` | 从`xy`值的偏移（以磅为单位） |
| `'polar'` | 您可以为注释指定`theta`，`r`，即使在笛卡尔坐标图中也是如此。请注意，如果使用极轴，则不需要为坐标系指定极轴，因为这是原生`'data'`坐标系。 |

### 示例1

```py
from matplotlib.patches import ConnectionPatch
import matplotlib.pyplot as plt

fig, (ax1, ax2) = plt.subplots(1, 2,
                               figsize =(6, 3))

# Draw a simple arrow between
# two points in axes coordinates
# within a single axes.
xyA = (0.2, 0.2)
xyB = (0.8, 0.8)
coordsA = "data"
coordsB = "data"
con = ConnectionPatch(xyA, xyB,
                      coordsA, coordsB,
                      arrowstyle ="-|>",
                      shrinkA = 5, shrinkB = 5,
                      mutation_scale = 20,
                      fc ="w")

ax1.plot([xyA[0], xyB[0]], [xyA[1],
                            xyB[1]], "o")
ax1.add_artist(con)

# Draw an arrow between the
# same point in data coordinates,
# but in different axes.
xy = (0.3, 0.2)
con = ConnectionPatch(
    xyA = xy, coordsA = ax2.transData,
    xyB = xy, coordsB = ax1.transData,
    arrowstyle ="->", shrinkB = 5)

ax2.add_artist(con)

# Draw a line between the different
# points, defined in different coordinate
# systems.
con = ConnectionPatch(
    # in axes coordinates
    xyA =(0.6, 1.0), coordsA = ax2.transAxes,
    # x in axes coordinates, y in data coordinates
    xyB =(0.0, 0.2), coordsB = ax2.get_yaxis_transform(),
    arrowstyle ="-")

ax2.add_artist(con)

ax1.set_xlim(0, 1)
ax1.set_ylim(0, 1)
ax2.set_xlim(0, .5)
ax2.set_ylim(0, .5)

plt.show()
```

**输出：**

![](img/ed38e1edbc90be8a6a5197670bed8c6e.png)

### 示例2

```py
import matplotlib.pyplot as plt
from matplotlib.patches import ConnectionPatch
import numpy as np

# make figure and assign axis
# objects
fig = plt.figure(figsize =(9, 5))
ax1 = fig.add_subplot(121)
ax2 = fig.add_subplot(122)
fig.subplots_adjust(wspace = 0)

# pie chart parameters
ratios = [.27, .56, .17]
explode = [0.1, 0, 0]

# rotate so that first wedge is
# split by the x-axis
angle = -180 * ratios[0]
ax1.pie(ratios, autopct ='%1.1f%%',
        startangle = angle,
        explode = explode)

# bar chart parameters

xpos = 0
bottom = 0
ratios = [.33, .54, .07, .06]
width = .2
colors = [[.1, .3, .5],
          [.1, .3, .3],
          [.1, .3, .7],
          [.1, .3, .9]]

for j in range(len(ratios)):
    height = ratios[j]
    ax2.bar(xpos, height, width,
            bottom = bottom,
            color = colors[j])

    ypos = bottom + ax2.patches[j].get_height() / 2
    bottom += height
    ax2.text(xpos,
             ypos,
             "%d%%" % (ax2.patches[j].get_height() * 100),
             ha ='center')

ax2.set_title('')
ax2.legend(('50-65', 'Over 65', '35-49', 'Under 35'))
ax2.axis('off')
ax2.set_xlim(- 2.5 * width, 2.5 * width)

# use ConnectionPatch to draw
# lines between the two plots
# get the wedge data
theta1, theta2 = ax1.patches[0].theta1, ax1.patches[0].theta2
center, r = ax1.patches[0].center, ax1.patches[0].r
bar_height = sum([item.get_height() for item in ax2.patches])

# draw top connecting line
x = r * np.cos(np.pi / 180 * theta2) + center[0]
y = np.sin(np.pi / 180 * theta2) + center[1]
con = ConnectionPatch(xyA =(-width / 2, bar_height),
                      coordsA = ax2.transData,
                      xyB =(x, y),
                      coordsB = ax1.transData)

con.set_color([0, 0, 0])
con.set_linewidth(4)
ax2.add_artist(con)

# draw bottom connecting line
x = r * np.cos(np.pi / 180 * theta1) + center[0]
y = np.sin(np.pi / 180 * theta1) + center[1]

con = ConnectionPatch(xyA =(-width / 2, 0),
                      coordsA = ax2.transData,
                      xyB =(x, y),
                      coordsB = ax1.transData)

con.set_color([0, 0, 0])
ax2.add_artist(con)
con.set_linewidth(4)

plt.show()
```

**输出：**

![](img/2a6d906412ceafc13533435d19c26e7c.png)