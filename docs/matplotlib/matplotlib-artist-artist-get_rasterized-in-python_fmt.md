# Python 中的 `matplotlib.artist.Artist.get_rasterized()`

> 原文: [https://www.geeksforgeeks.org/matplotlib-artist-artist-get_rasterized-in-python/](https://www.geeksforgeeks.org/matplotlib-artist-artist-get_rasterized-in-python/)

`Matplotlib` 是 Python 中的一个库，是 `NumPy` 库的数值-数学扩展。`Artist` 类包含抽象基类，用于渲染到图形画布中的对象。图形中所有可见的元素都是 `Artist` 的子类。

## `matplotlib.artist.Artist.get_rasterized()` 方法

`matplotlib` 库的 `artist` 模块中的 `get_rasterized()` 方法用于获取是否要栅格化艺术家。

> **语法:** `artist.get_rasterized(self)`
>
> **参数:** 该方法不接受任何参数。
>
> **返回:** 此方法返回艺术家是否要光栅化。

以下示例说明了 `matplotlib` 中的 `matplotlib.artist.Artist.get_rasterized()` 函数:

**例 1:**

```py
# Implementation of matplotlib function
from matplotlib.artist import Artist
import numpy as np
import matplotlib.pyplot as plt

d = np.arange(100).reshape(10, 10)
xx, yy = np.meshgrid(np.arange(11), np.arange(11))

fig, ax = plt.subplots()

ax.set_aspect(1)
m = ax.pcolormesh(xx, yy, d)

if Artist.get_rasterized(m)== None:
    Artist.set_rasterized(m, True)

fig.suptitle('matplotlib.artist.Artist.get_rasterized()\
function Example', fontweight ="bold")

plt.show()
```

**输出:**
![](img/219b86eaad390a58b23e044cbbd61fec.png)

**例 2:**

```py
# Implementation of matplotlib function
from matplotlib.artist import Artist
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

if Artist.get_rasterized(im)== None:
    Artist.set_rasterized(im, False)

fig.suptitle('matplotlib.artist.Artist.get_rasterized()\
function Example', fontweight ="bold")
plt.show()
```

**输出:**
![](img/f3b773d89a018e1abee09635fbe08522.png)