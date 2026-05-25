# 如何使用 Matplotlib 在 Python 中可视化稀疏矩阵？

> 原文: [https://www.geeksforgeeks.org/how-to-visualize-sparse-matrix-in-python-using-matplotlib/](https://www.geeksforgeeks.org/how-to-visualize-sparse-matrix-in-python-using-matplotlib/)

`Matplotlib` 是 Python 中一个惊人的可视化库，用于数组的 2D 图。`Matplotlib` 绘图库是一个基于 `NumPy` 阵列的多平台数据可视化库，旨在与更广泛的 `SciPy` 堆栈协同工作。

## 使用 Matplotlib 可视化稀疏矩阵

`spy()` 是一个类似于 `matplotlib` `imshow()` 函数的函数，用于将数组可视化为一个图像，但是它是在稀疏矩阵而不是密集矩阵的情况下使用的。一个*稀疏矩阵*是一个大部分元素为零的矩阵。

![稀疏矩阵及其表示](img/e1e872b5ba9b9cca44c1992fdf5acf04.png)

`spy()` 函数使用两种绘图样式来可视化数组，它们是：

*   图像样式
*   标记样式

这两种样式都可以用于全数组，但是在 `spmatrix` 实例中，只有标记样式有效。如果 `marker` 或 `markersize` 为 `None`，则使用 `imshow()` 函数，剩余的所有关键字参数都传递给该函数；否则，将返回一个 `Line2D` 对象，其 `marker` 值决定标记类型，任何剩余的关键字参数将传递给 `plot()` 功能。

> **语法:** `matplotlib.pyplot.spy(Z, precision=0, marker=None, markersize=None, aspect='equal', origin='upper', **kwargs)`
>
> **返回值:**
>
> 返回类型取决于打印样式，即 `AxesImage` 或 `Line2D`。

**参数:**

| 参数 | 价值 | 使用 |
| --- | --- | --- |
| `Z` | 类数组(M，N) | 要绘制的数组 |
| `precision` | 浮动或 `'present'`，可选<br>默认: `0` | 如果 `precision` 为 `0`，将绘制任何非零值；否则，将绘制 `|Z| > precision` 的值。<br>对于 `spmatrix` 实例，有一种特殊情况: 如果 `precision` 为 `'present'`，则数组中存在的任何值都将被绘制，即使它完全为零。 |
| `origin` | `{ 'upper'，'lower' }`，可选<br>默认: `'upper'` | 将数组的 `[0，0]` 索引放在轴的左上角或左下角。 |
| `aspect` | `{ 'equal'，'auto'，None 或浮动 }`，可选<br>默认: `'equal'` | 它控制轴的纵横比。该方面与图像特别相关，因为它可能使图像失真，即像素不是正方形。<br>*   `'equal'`: 确保纵横比为 1。像素将是方形的。<br>*   `'auto'`: 轴保持固定，纵横比调整，以便数据适合轴。通常，这将导致非方形像素。<br>*   `None`: 使用 `rcParams["image.aspect"]` |

**其他参数: `**kwargs`**

这些是有助于获得不同打印样式的附加参数。

| 属性 | 描述 |
| --- | --- |
| `agg_filter` | 一个过滤函数，接受 `(m，n，3)` 浮点数组和 `dpi` 值，并返回 `(m，n，3)` 数组 |
| `alpha` | 浮动或无 |
| `animated` | 布尔值 |
| `antialiased` | 布尔值 |
| `clip_box` | `Bbox` |
| `clip_on` | 布尔值 |
| `clip_path` | `Patch` 或 `(Path，Transform)` 或无 |
| `color` | 颜色 |
| `contains` | 可调用对象 |
| `dash_capstyle` | `{ 'butt'，'round'，'projecting' }` |
| `dash_joinstyle` | `{ 'miter'，'round'，'bevel' }` |
| `dashes` | 浮动顺序 (以磅为单位的开/关油墨) 或 `(无，无)` |
| `data` | `(2，N)` 阵列或两个 1D 阵列 |
| `drawstyle` | `{ 'default'，'steps'，'steps-pre'，'steps-mid'，'steps-post' }` |
| `figure` | `Figure` |
| `fillstyle` | `{"full"，"left"，"right"，"bottom"，"top"，"none"}` |
| `gid` | 字符串 |
| `in_layout` | 布尔值 |
| `label` | 字符串 |
| `linestyle` | `{'-'，'--'，'-.'，':'，""，(offset，on-off-seq)，…}` |
| `linewidth` | 浮动值 |
| `marker` | 标记样式 |
| `markeredgecolor` | 颜色 |
| `markeredgewidth` | 浮动值 |
| `markerfacecolor` | 颜色 |
| `markerfacecoloralt` | 颜色 |
| `markersize` | 浮动值 |
| `markevery` | 无或整数或 (整数，整数) 或切片或列表[整数] 或浮动或 (浮动，浮动) |
| `path_effects` | `AbstractPathEffect` |
| `picker` | 浮动或可调用 `[[Artist，Event]，Tuple[bool，dict]]` |
| `pickradius` | 浮动值 |
| `rasterized` | 布尔值或无 |
| `sketch_params` | `(scale:float，length:float，randomness:float)` |
| `snap` | 布尔值或无 |
| `solid_capstyle` | `{ 'butt'，'round'，'projecting' }` |
| `solid_joinstyle` | `{ 'miter'，'round'，'bevel' }` |
| `transform` | `matplotlib.transforms.Transform` |
| `url` | 字符串 |
| `visible` | 布尔值 |
| `xdata` | 1D 阵列 |
| `ydata` | 1D 阵列 |
| `zorder` | 浮动值 |

**例 1:**

```python
# Implementation of matplotlib spy function
import matplotlib.pyplot as plt
import numpy as np

x = np.random.randn(50, 50)

x[15, :] = 0.
x[:, 40] = 0.

plt.spy(x)
```

**输出:**
![Visualize sparse matrix python](img/34f04483a49a2f10e724ef421dfa8e48.png)

**例 2:**

```python
# Implementation of matplotlib spy function
import matplotlib.pyplot as plt
import numpy as np

x = np.random.randn(50, 50)
x[15, :] = 0.
x[:, 40] = 0.

plt.spy(x, precision = 0.1, markersize = 5)
```

**输出:**
![Visualize sparse matrix python](img/3328aec0436fd23899da5ddc9a9acbcb.png)