# matplotlib.axes.Axes.set_rasterized()

> 原文: [https://www.geeksforgeeks.org/matplotlib-axes-axes-set_rasterized-in-python/](https://www.geeksforgeeks.org/matplotlib-axes-axes-set_rasterized-in-python/)

[Matplotlib](https://www.geeksforgeeks.org/python-introduction-matplotlib/) 是 Python 中的一个库，是 NumPy 库的数值-数学扩展。`Axes` 类包含了大部分的图形元素：轴、刻度、`Line2D`、文本、多边形等，并设置坐标系。`Axes` 的实例通过回调属性支持回调。

## matplotlib.axes.Axes.set_rasterized() 函数

`matplotlib` 库的 `Axes` 模块中的 `axes.set_rasterized()` 函数用于在矢量后端输出中强制栅格化（位图）绘制。

> **语法:** `Axes.set_rasterized(self, rasterized)`
>
> **参数:** 该方法只接受一个参数。
>
> *   `rasterized`: 该参数为布尔值。
>
> **返回:** 该方法不返回值。

下面的例子说明了 `matplotlib.axes.Axes.set_rasterized()` 函数在 `matplotlib.axes` 中的作用：

**例 1:**

```py
# Implementation of matplotlib function
import numpy as np
import matplotlib.pyplot as plt

d = np.arange(100).reshape(10, 10)
xx, yy = np.meshgrid(np.arange(11), np.arange(11))

fig, ax = plt.subplots()

ax.set_aspect(1)
m = ax.pcolormesh(xx, yy, d)
m.set_rasterized(True)

fig.suptitle('matplotlib.axes.Axes.set_rasterized() \
function Example', fontweight ="bold")

plt.show()
```

**输出:**
![](img/e0f23fd490eb0a04d5c588c0b0779311.png)

**例 2:**

```py
# Implementation of matplotlib function
import matplotlib.pyplot as plt
import matplotlib.colors as mcolors
import matplotlib.gridspec as gridspec
import numpy as np

arr = np.arange(100).reshape((10, 10))
norm = mcolors.Normalize(vmin = 0., vmax = 100.)

pc_kwargs = {'cmap': 'plasma', 'norm': norm}

fig, ax = plt.subplots( )

im = ax.pcolormesh(arr, **pc_kwargs)
fig.colorbar(im, ax = ax, shrink = 0.6)

ax.set_rasterized(False)

fig.suptitle('matplotlib.axes.Axes.set_rasterized()\
 function Example', fontweight ="bold")

plt.show()
```

**输出:**
![](img/e61a6b03729de40b43083096f14fca41.png)