# matplotlib.patches.PathPatch

## 简介

> 原文: [https://www.geeksforgeeks.org/matplotlib-patches-pathpatch-in-python/](https://www.geeksforgeeks.org/matplotlib-patches-pathpatch-in-python/)

**[Matplotlib](https://www.geeksforgeeks.org/python-matplotlib-an-overview/)** 是 Python 中一个惊人的可视化库，用于数组的 2D 图。Matplotlib 绘图库是一个基于 NumPy 阵列的多平台数据可视化库，旨在与更广泛的 SciPy 堆栈协同工作。

## matplotlib.patches.PathPatch

`matplotlib.patches.PathPatch` 类用于绘制一般的多曲线路径面片。

> **语法:** `class matplotlib.patches.PathPatch(path, **kwargs)`
>
> **参数:**
>
> *   **path:** 路径是一个 `matplotlib.path.Path` 对象。

下表列出了有效的 kwargs 参数:

| 属性 | 描述 |
| --- | --- |
| `agg_filter` | 接受 (m, n, 3) 浮点数组和返回 (m, n, 3) 数组的 dpi 值的筛选函数 |
| `alpha` | 浮动或无 |
| `animated` | 布尔值 |
| `antialiased` 或 `aa` | 布尔值或无 |
| `capstyle` | { 'butt', 'round', 'projecting' } |
| `clip_box` | `Bbox` |
| `clip_on` | 布尔值 |
| `clip_path` | [(Path, Transform) \| Patch \| None] |
| `color` | rgba 元组的颜色或序列 |
| `contains` | 可调用 |
| `edgecolor` 或 `ec` 或 `edgecolors` | 颜色或无或 "auto" |
| `facecolor` 或 `fc` 或 `facecolors` | 颜色或无 |
| `figure` | `Figure` |
| `fill` | 布尔值 |
| `gid` | 字符串 |
| `hatch` | {'/', '\', '|', '-', '+', 'x', 'o', 'O', '.', '*'} |
| `in_layout` | 布尔值 |
| `joinstyle` | { 'miter', 'round', 'bevel' } |
| `linestyle` 或 `ls` | {'-', '--', '-.', ':', '', (offset, on-off-seq), ...} |
| `linewidth` 或 `lw` | 浮动或无 |
| `path_effects` | `AbstractPathEffect` |
| `picker` | None、布尔、浮动或可调用 |
| `rasterized` | 布尔或无 |
| `sketch_params` | (scale: float, length: float, randomness: float) |
| `snap` | 布尔或无 |
| `transform` | `matplotlib.transforms.Transform` |
| `url` | 字符串 |
| `visible` | 布尔值 |
| `zorder` | 浮动 |

## 示例 1

```py
import numpy as np
import matplotlib.cm as cm
import matplotlib.pyplot as plt
import matplotlib.cbook as cbook
from matplotlib.path import Path
from matplotlib.patches import PathPatch

delta = 0.025
x = y = np.arange(-3.0, 3.0, delta)
X, Y = np.meshgrid(x, y)
Z1 = np.exp(-X**2 - Y**2)
Z2 = np.exp(-(X - 1)**2 - (Y - 1)**2)
Z = (Z1 - Z2) * 2

path = Path([[0, 1], [1, 0], [0, -1], [-1, 0], [0, 1]])
patch = PathPatch(path, facecolor ='none')

fig, ax = plt.subplots()
ax.add_patch(patch)

im = ax.imshow(Z, interpolation ='bilinear', cmap = cm.gray,
               origin ='lower', extent =[-3, 3, -3, 3],
               clip_path = patch, clip_on = True)
im.set_clip_path(patch)

plt.show()
```

**输出:**
![](img/852ccdd03d6ad18bccac7a0156a25997.png)

## 示例 2

```py
import matplotlib.pyplot as plt 
import numpy as np
from matplotlib.path import Path
from matplotlib.patches import PathPatch

fig = plt.figure()

ax = fig.add_subplot(111, aspect ='equal') 
path = Path([[0, 0], [0, 1], [1, 0], [0, 0]])
patch = PathPatch(path, facecolor ='none')
ax.add_patch(patch)

Z, Z2 = np.meshgrid(np.linspace(0, 1), np.linspace(0, 1))

im = plt.imshow(Z-Z2, 
                interpolation ='bilinear', 
                cmap = plt.cm.RdYlGn,
                origin ='lower',
                extent =[0, 1, 0, 1],
                clip_path = patch,
                clip_on = True)

im.set_clip_path(patch)

ax.set_xlim((0, 1)) 
ax.set_ylim((0, 1))

plt.show()
```

**输出:**
![](img/11ef3005fb23178998dc742a500987bf.png)