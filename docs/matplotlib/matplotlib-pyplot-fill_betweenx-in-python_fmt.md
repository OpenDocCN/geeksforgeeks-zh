# matplotlib.pyplot.fill_betweenx() 用法详解

> 原文: [https://www.geeksforgeeks.org/matplotlib-pyplot-fill_betweenx-in-python/](https://www.geeksforgeeks.org/matplotlib-pyplot-fill_betweenx-in-python/)

[Matplotlib](http://geeksforgeeks.org/python-matplotlib-an-overview/) 是 Python 中一个惊人的可视化库，用于数组的 2D 图。Matplotlib 是一个多平台数据可视化库，构建在 NumPy 数组上，旨在与更广泛的 SciPy 堆栈一起工作。

## matplotlib.pyplot.fill_betweenx()

`matplotlib.pyplot.fill_betweenx()` 用于填充两条竖曲线之间的区域。两点 `(x1, y)` 和 `(x2, y)` 定义了曲线。这将创建一个或多个描述填充区域的多边形。`where` 参数可用于选择性填充某些区域。默认情况下，边直接连接给定点。如果填充需要是阶跃函数，则使用 `step` 参数。

> **语法:** `matplotlib.pyplot.fill_betweenx(y, x1, x2=0, where=None, step=None, interpolate=False, *, data=None, **kwargs)`
> **参数:**
> *   `y`: 是长度 n 的数组，这些是定义曲线的节点的 y 坐标。
> *   `x1`: 是长度为 N 的数组或者标量。这表示定义第一条曲线的节点的 x 坐标。
> *   `x2`: 是长度为 N 的数组，本质上是可选的。其默认值为 0。这表示定义第二条曲线的节点的 x 坐标。
> *   `where`: 为长度为 n 的布尔值数组，定义是否需要排除部分垂直区域被填充。需要注意的是，这个定义意味着两个假值之间的一个孤立的真值不会被填充。相邻的假值不会填充真值的两边。
> *   `interpolate`: 是接受布尔值的可选参数。仅当使用了 `where` 并且两条曲线相互交叉时才相关。语义上如果一般用于 `x1 > x2` 或类似的情况。默认情况下，填充区域将放置在定义填充多边形区域的 `y` 阵列位置。有交集的 `y` 的部分被简单地裁剪。将此参数设置为 `True` 将导致实际交点的计算，并延伸到填充区域直至点。
> *   `step`: 这是一个可选参数，接受三个值中的一个，即 `'pre'`、`'post'` 和 `'mid'`。这用于指定步骤将在哪里发生。
>     *   `'pre'`: 从每个 x 位置开始，y 值持续向左，即区间 `(x[i-1], x[i])` 的值为 `y[i]`。
>     *   `'post'`: 从每个 x 位置开始，y 值不断向右延续，即区间 `(x[i], x[i+1])` 的值为 `y[i]`。
>     *   `'mid'`: 这些步骤发生在 x 位置的中间。
>
> **返回:** 它从多边形集合中返回一个绘制的多边形。

**其他参数:** `**kwargs` 包含来自控制多边形属性的 `PolyCollection` 的关键字；

<figure class="table">

| 属性 | 描述 |
| --- | --- |
| `agg_filter` | 接受 `(m, n, 3)` 浮点数组和返回 `(m, n, 3)` 数组的 dpi 值的筛选函数 |
| `alpha` | 浮动或无 |
| `animated` | 布尔值 |
| `array` | ndarray(阵列) |
| `capstyle` | `{ 'butt', 'round', 'projecting' }` |
| `clim` | 长度为 2 的浮动序列；可能会在具有 `vmin` 和 `vmax` kwargs 的方法中被覆盖。 |
| `cmap` | 彩色地图或注册彩色地图 |
| `antialiased` 或 `aa` 或 `antialiaseds` | 布尔或布尔序列 |
| `clipbox` | Bbox |
| `clip_on` | 布尔值 |
| `clip_path` | `[(Path, Transform)|Patch|None]` |
| `color` | rgba 元组的颜色或序列 |
| `contains` | 可调用对象 |
| `edgecolor` 或 `ec` 或 `edgecolors` | 颜色或颜色序列或 `'face'` |
| `facecolor` 或 `fc` 或 `facecolors` | 颜色或颜色序列 |
| `figure` | 图形 |
| `gid` | 字符串 |
| `hatch` | `{ '/', '\\', '|', '-', '+', 'x', 'o', 'O', '.', '*' }` |
| `in_layout` | 布尔值 |
| `joinstyle` | `{ 'miter', 'round', 'bevel' }` |
| `linestyle` 或 `dashes` | `{ '-', '--', '-.', ':', '', (offset, on-off-seq), … }` |
| `linewidth` 或 `linewidths` 或 `lw` | 浮动或浮动序列 |
| `norm` | 归一化对象 |
| `offset_position` | `{“screen”, “data”}` |
| `offsets` | 浮动或浮动序列 |
| `path_effects` | 抽象路径效应 |
| `picker` | None、布尔、浮点或可调用 |
| `pickradius` | 浮动 |
| `rasterized` | 布尔或无 |
| `sketch_params` | `(scale: float, length: float, randomness: float)` |
| `snap` | 布尔或无 |
| `transform` | matplotlib.transforms.Transform |
| `url` | 字符串 |
| `urls` | 列表[字符串]或无 |
| `visible` | 布尔值 |
| `xdata` | 1D 阵列 |
| `ydata` | 1D 阵列 |

</figure>

**例 1:**

```py
import matplotlib.pyplot as plt
import numpy as np

a = np.linspace(0, 2 * 3.14, 50)
b = np.sin(a)

plt.fill_betweenx(a, b, 0,
                  where=(a > -0.5) & (a <= 1),
                  color='g')

plt.plot(a, b)
```

**输出:**

![python-matplotlib-fillbetweenx-1](img/b0ccfacffa758c6a46d7396572c21800.png)

**例 2:**

```py
import pylab as plt
import numpy as np

N = np.linspace(0, 3, 200)
A1 = N**2 + 3
A2 = np.exp(N) + 2
A3 = np.cos(N)

plt.plot(N, A1, lw=3)
plt.plot(N, A2, lw=3)
plt.plot(N, A3, lw=3)

plt.fill_betweenx(N, A1, A2,
                  color='r',
                  alpha=.5)
plt.fill_betweenx(N, A1, A3,
                  color='g',
                  alpha=.5)

plt.show()
```

**输出:**

![python-matplotlib-fillbetweenx-2](img/b5d0ea06e942e530913fdd4cef4ba423.png)