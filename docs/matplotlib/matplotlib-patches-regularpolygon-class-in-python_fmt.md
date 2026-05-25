# Python 中的 `matplotlib.patches.RegularPolygon` 类

> 原文: [https://www.geeksforgeeks.org/matplotlib-patches-regularpolygon-class-in-python/](https://www.geeksforgeeks.org/matplotlib-patches-regularpolygon-class-in-python/)

[**Matplotlib**](https://www.geeksforgeeks.org/python-matplotlib-an-overview/) 是 Python 中一个惊人的可视化库，用于数组的 2D 图。Matplotlib 是一个多平台数据可视化库，构建在 NumPy 数组上，旨在与更广泛的 SciPy 堆栈一起工作。

## `matplotlib.patches.RegularPolygon`

`matplotlib.patches.RegularPolygon` 类用于添加正多边形面片。

> **语法:** `class matplotlib.patches.RegularPolygon(xy, numVertices, radius=5, orientation=0, **kwargs)`
> **参数:**
> *   `xy`: 一个长度为 2 的元组 `(x, y)` 的中心。
> *   `numVertices`: 表示顶点数。
> *   `radius`: 从中心到每个顶点的距离。
> *   `orientation`: 用于旋转多边形（以弧度为单位）。

下表列出了有效的 `kwargs`

| 属性 | 描述 |
| --- | --- |
| `agg_filter` | 接受 `(m, n, 3)` 浮点数组和返回 `(m, n, 3)` 数组的 dpi 值的筛选函数 |
| `alpha` | 浮动或无 |
| `animated` | 布尔值 |
| `antialiased` 或 `aa` | 未知的 |
| `capstyle` | `{ 'butt', 'round', 'projecting' }` |
| `clip_box` | `Bbox` |
| `clip_on` | 布尔值 |
| `clip_path` | `[(Path, Transform) | Patch | None]` |
| `color` | rgba 元组的颜色或序列 |
| `contains` | 可调用 |
| `edgecolor` 或 `ec` 或 `edgecolors` | 颜色或无或 `'auto'` |
| `facecolor` 或 `fc` 或 `facecolors` | 颜色或无 |
| `figure` | `Figure` |
| `fill` | 布尔值 |
| `gid` | 字符串 |
| `hatch` | `{ '/', '\', '|', '-', '+', 'x', 'o', 'O', '.', '*' }` |
| `in_layout` | 布尔值 |
| `joinstyle` | `{ 'miter', 'round', 'bevel' }` |
| `linestyle` 或 `ls` | `{ '-', '--', '-.', ':', '', (offset, on-off-seq), ... }` |
| `linewidth` 或 `lw` | 浮动或无 |
| `path_effects` | `AbstractPathEffect` |
| `picker` | 无、布尔、浮点或可调用 |
| `rasterized` | 布尔或无 |
| `sketch_params` | `(scale: float, length: float, randomness: float)` |
| `snap` | 布尔或无 |
| `transform` | `matplotlib.transforms.Transform` |
| `url` | 字符串 |
| `visible` | 布尔值 |
| `zorder` | 浮动 |

**例 1:**

```py
import matplotlib.pyplot as plt
from matplotlib.patches import RegularPolygon
import numpy as np

coord = [[0, 0, 0],
         [0, 1, -1],
         [-1, 1, 0],
         [-1, 0, 1],
         [0, -1, 1],
         [1, -1, 0],
         [1, 0, -1]]

colors = [["Green"],
          ["Green"],
          ["Green"],
          ["Green"],
          ["Green"],
          ["Green"],
          ["Green"]]

labels = [['1'], ['2'],
          ['3'], ['4'],
          ['5'], ['6'],
          ['7']]

# Horizontal cartesian coords
hcoord = [c[0] for c in coord]

# Vertical cartersian coords
vcoord = [2. * np.sin(np.radians(60)) * (c[1] - c[2]) /3.
          for c in coord]

fig, ax = plt.subplots(1)
ax.set_aspect('equal')

# Add some coloured hexagons
for x, y, c, l in zip(hcoord, vcoord, colors, labels):
    # matplotlib understands lower
    # case words for colours
    color = c[0].lower()
    hex = RegularPolygon((x, y),
                         numVertices = 6,
                         radius = 2. / 3.,
                         orientation = np.radians(30),
                         facecolor = color,
                         alpha = 0.2,
                         edgecolor ='k')
    ax.add_patch(hex)
    # Also add a text label
    ax.text(x, y + 0.2, l[0], ha ='center',
            va ='center', size = 20)

# add scatter points in hexagon centers
ax.scatter(hcoord, vcoord, c =[c[0].lower()
                               for c in colors],
           alpha = 0.5)

plt.show()
```

**输出:**

![](img/0fc18802afc939118c79acde4dccb32f.png)

**例 2:**

```py
import matplotlib.pyplot as plt
from matplotlib.patches import RegularPolygon
from matplotlib.collections import PatchCollection
import numpy as np

xy = np.random.random((10, 2))
z = np.random.random(10)

patches = [RegularPolygon((x, y),
                          5, 0.1)
           for x, y in xy]

collection = PatchCollection(patches,
                             array = z,
                             edgecolors ='brown',
                             lw = 2)

fig, ax = plt.subplots()

ax.patch.set(facecolor ='green')
ax.add_collection(collection)
ax.autoscale()

plt.show()
```

**输出:**

![](img/9d045fa8b67432a98d6abb058d82d509.png)