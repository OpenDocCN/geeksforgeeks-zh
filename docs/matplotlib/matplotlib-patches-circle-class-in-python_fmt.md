# Python 中的 Matplotlib.patches.Circle 类

> 原文: [https://www.geeksforgeeks.org/matplotlib-patches-circle-class-in-python/](https://www.geeksforgeeks.org/matplotlib-patches-circle-class-in-python/)

[Matplotlib](https://www.geeksforgeeks.org/python-matplotlib-an-overview/) 是 Python 中一个惊人的可视化库，用于数组的 2D 图。Matplotlib 是一个多平台数据可视化库，构建在 NumPy 数组上，旨在与更广泛的 SciPy 堆栈一起工作。

## matplotlib.patches.Circle

`matplotlib.patches.Circle` 类用于在给定半径的给定中心 `xy = (x, y)` 创建圆形面片。它使用贝塞尔曲线，更接近无标度圆。

> **语法:** `class matplotlib.patches.Circle(xy, radius=5, **kwargs)`
>
> **参数:**
>
> *   `xy`: 是圆心。
> *   `radius`: 设置要画圆的半径。它的默认值是 5 个单位，并且是可选的。

下表提供了可选的有效 kwargs

| 属性 | 描述 |
| --- | --- |
| `agg_filter` | 接受 (m, n, 3) 浮点数组和返回 (m, n, 3) 数组的 dpi 值的筛选函数 |
| `alpha` | 浮动或无 |
| `animated` | 布尔值 |
| `antialiased` 或 `aa` | 未知的 |
| `capstyle` | { 'butt', 'round', 'projecting' } |
| `clip_box` | Bbox |
| `clip_on` | 布尔值 |
| `clip_path` | [(路径, 转换) | 补丁 | 无] |
| `color` | rgba 元组的颜色或序列 |
| `contains` | 可调用 |
| `edgecolor` 或 `ec` 或 `edgecolors` | 颜色或无或 'auto' |
| `facecolor` 或 `fc` 或 `facecolors` | 颜色或无 |
| `figure` | 图形 |
| `fill` | 布尔值 |
| `gid` | 字符串 |
| `hatch` | {'/', '\', '|', '-', '+', 'x', 'o', 'O', '.', '*'} |
| `in_layout` | 布尔值 |
| `joinstyle` | { 'miter', 'round', 'bevel' } |
| `linestyle` 或 `ls` | {'-', '--', '-.', ':', '', (offset, on-off-seq), ...} |
| `linewidth` 或 `lw` | 浮动或无 |
| `path_effects` | 抽象路径效应 |
| `picker` | 无、布尔、浮动或可调用 |
| `rasterized` | 布尔或无 |
| `sketch_params` | (比例: 浮动, 长度: 浮动, 随机性: 浮动) |
| `snap` | 布尔或无 |
| `transform` | `matplotlib.transforms.Transform` |
| `url` | 字符串 |
| `visible` | 布尔值 |
| `zorder` | 浮动 |

### 例 1:

```py
import numpy as np
from matplotlib.patches import Circle
from matplotlib.collections import PatchCollection
import matplotlib.pyplot as plt
from matplotlib import cm
from matplotlib import animation

fig, ax = plt.subplots()

patches = []
# create circles with random sizes
# and locations
N = 12 # number of circles
x = np.random.rand(N)
y = np.random.rand(N)
radii = 0.1 * np.random.rand(N)
for x1, y1, r in zip(x, y, radii):
    circle = Circle((x1, y1), r)
    patches.append(circle)

# add these circles to a collection
p = PatchCollection(patches, cmap = cm.prism, alpha = 0.4)
ax.add_collection(p)

def animate(i):
    # random index to color map
    colors = 100 * np.random.rand(len(patches))
    # set new color colors
    p.set_array(np.array(colors))
    return p,

ani = animation.FuncAnimation(fig, animate,
                              frames = 50, interval = 50)

plt.show()
```

**输出:**
![](img/65389340844323ff402fe27cf6138f39.png)

### 例 2:

```py
import numpy as np
import matplotlib
from matplotlib.patches import Circle, Wedge, Polygon, Ellipse
from matplotlib.collections import PatchCollection
import matplotlib.pyplot as plt
import matplotlib.patches as matpatches

fig, ax = plt.subplots(figsize =(8, 8))
patches = []

circle = Circle((2, 2), 2)
patches.append(circle)

polygon = matpatches.PathPatch(patches[0].get_path())
patches.append(polygon)

colors = 2 * np.random.rand(len(patches))
p = PatchCollection(patches,
                    cmap = matplotlib.cm.jet,
                    alpha = 0.4)

p.set_array(np.array(colors))
ax.add_collection(p)

plt.axis([-10, 10, -10, 10])

plt.show()

contain2 = patches[0].get_path().contains_points([[0.5, 0.5],
                                                  [1.0, 1.0]])
contain3 = patches[0].contains_point([0.5, 0.5])
contain4 = patches[0].contains_point([1.0, 1.0])
```

**输出:**
![](img/97cd6aef352c845819ac18cc920b2e52.png)