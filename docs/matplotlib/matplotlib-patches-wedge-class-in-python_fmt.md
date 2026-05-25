# Python 中的 Matplotlib.patches.Wedge 类

> 原文: [https://www.geeksforgeeks.org/matplotlib-patches-wedge-class-in-python/](https://www.geeksforgeeks.org/matplotlib-patches-wedge-class-in-python/)

[**Matplotlib**](https://www.geeksforgeeks.org/python-matplotlib-an-overview/) 是 Python 中一个惊人的可视化库，用于数组的 2D 图。Matplotlib 是一个多平台数据可视化库，构建在 NumPy 数组上，旨在与更广泛的 SciPy 堆栈一起工作。

## `matplotlib.patches.Wedge`

`matplotlib.patches.Wedge` 类用于在绘图中添加楔形面片。楔子以 `xy = (x, y)` 为中心，半径为 `r`，它扫过 `theta1` 到 `theta2`（以度为单位）。如果给定 `width`，部分楔形从内半径 `r - width` 画到外半径 `r`。

> **语法:** `class matplotlib.patches.Wedge(center, r, theta1, theta2, width=None, **kwargs)`
> **参数:**
> 1.  `center`: 楔子的中心点。
> 2.  `r`: 楔块的半径。
> 3.  `theta1`: 第一扫掠角度。
> 4.  `theta2`: 第二扫掠角。
> 5.  `width`: 扫掠的宽度。

`kwargs` 属性如下表所示:

| 属性 | 描述 |
| --- | --- |
| `agg_filter` | 接受 `(m, n, 3)` 浮点数组和返回 `(m, n, 3)` 数组的 dpi 值的筛选函数 |
| `alpha` | 浮动或无 |
| `animated` | 布尔值 |
| `antialiased` 或 `aa` | 布尔值或无 |
| `capstyle` | `{'butt', 'round', 'projecting'}` |
| `clip_box` | `Bbox` |
| `clip_on` | 布尔值 |
| `clip_path` | `[(Path, Transform) | Patch | None]` |
| `color` | rgba 元组的颜色或序列 |
| `contains` | 可调用对象 |
| `edgecolor` 或 `ec` 或 `edgecolors` | 颜色或无或 `'auto'` |
| `facecolor` 或 `fc` 或 `facecolors` | 颜色或无 |
| `figure` | `Figure` |
| `fill` | 布尔值 |
| `gid` | 字符串 |
| `hatch` | `{'/', '\', '|', '-', '+', 'x', 'o', 'O', '.', '*'}` |
| `in_layout` | 布尔值 |
| `joinstyle` | `{'miter', 'round', 'bevel'}` |
| `linestyle` 或 `ls` | `{'-', '--', '-.', ':', '', (offset, on-off-seq), ...}` |
| `linewidth` 或 `lw` | 浮动或无 |
| `path_effects` | `AbstractPathEffect` |
| `picker` | 无、布尔、浮动或可调用对象 |
| `rasterized` | 布尔值或无 |
| `sketch_params` | `(scale: float, length: float, randomness: float)` |
| `snap` | 布尔值或无 |
| `transform` | `matplotlib.transforms.Transform` |
| `url` | 字符串 |
| `visible` | 布尔值 |
| `zorder` | 浮动 |

**例 1:**

```py
import numpy as np
from matplotlib.patches import Circle, Wedge, Polygon
from matplotlib.collections import PatchCollection
import matplotlib.pyplot as plt

# Fixing random state for reproducibility
np.random.seed(19680801)

fig, ax = plt.subplots()

resolution = 50  # the number of vertices
N = 3
x = np.random.rand(N)
y = np.random.rand(N)
radii = 0.1 * np.random.rand(N)
patches = []

for x1, y1, r in zip(x, y, radii):
    circle = Circle((x1, y1), r)
    patches.append(circle)

x = np.random.rand(N)
y = np.random.rand(N)
radii = 0.1 * np.random.rand(N)
theta1 = 360.0 * np.random.rand(N)
theta2 = 360.0 * np.random.rand(N)

for x1, y1, r, t1, t2 in zip(x, y, radii, theta1, theta2):
    wedge = Wedge((x1, y1), r, t1, t2)
    patches.append(wedge)

# Some limiting conditions on Wedge
patches += [
    Wedge((.3, .7), .1, 0, 360),             # Full circle
    Wedge((.7, .8), .2, 0, 360, width = 0.05),  # Full ring
    Wedge((.8, .3), .2, 0, 45),              # Full sector
    Wedge((.8, .3), .2, 45, 90, width = 0.10),  # Ring sector
]

for i in range(N):
    polygon = Polygon(np.random.rand(N, 2), True)
    patches.append(polygon)

colors = 100 * np.random.rand(len(patches))
p = PatchCollection(patches, alpha = 0.4)
p.set_array(np.array(colors))
ax.add_collection(p)
fig.colorbar(p, ax = ax)

plt.show()
```

**输出:**

![](img/98685f6a1c65745b1b8d7d23758d751b.png)

**例 2:**

```py
import numpy as np
import matplotlib.pyplot as plt

fig, ax = plt.subplots(figsize =(6, 3),
                       subplot_kw = dict(aspect ="equal"))

recipe = ["375 g flour",
          "75 g sugar",
          "250 g butter",
          "300 g berries"]

data = [float(x.split()[0]) for x in recipe]
ingredients = [x.split()[-1] for x in recipe]

def func(pct, allvals):
    absolute = int(pct / 100.*np.sum(allvals))
    return "{:.1f}%\n({:d} g)".format(pct, absolute)

wedges, texts, autotexts = ax.pie(data,
                                  autopct = lambda pct: func(pct, data),
                                  textprops = dict(color ="w"))

ax.legend(wedges, ingredients,
          title ="Ingredients",
          loc ="center left",
          bbox_to_anchor =(1, 0, 0.5, 1))

plt.setp(autotexts, size = 8, weight ="bold")

ax.set_title("Recipe for a pie")

plt.show()
```

**输出:**

![](img/a0bb17bfff1e5c19ea3fd2ce2b485541.png)