# 如何用 Python 中的 Matplotlib 绘制 2D 热图？

> 原文：[https://www.geeksforgeeks.org/how-to-draw-2d-heatmap-using-matplotlib-in-python/](https://www.geeksforgeeks.org/how-to-draw-2d-heatmap-using-matplotlib-in-python/)

二维热图是一种数据可视化工具，有助于以颜色的形式表示现象的严重程度。在 Python 中，我们可以使用 Matplotlib 包绘制二维热图。绘制二维热图有不同的方法，其中一些将在下面讨论。

## 方法一：使用 `matplotlib.pyplot.imshow()` 函数

> **语法：** `matplotlib.pyplot.imshow(X, cmap=None, norm=None, aspect=None, interpolation=None, alpha=None, vmin=None, vmax=None, origin=None, extent=None, shape=<deprecated argument>, filternorm=1, filterrad=4.0, imlim=<deprecated argument>, resample=None, url=None, *, data=None, **kwargs)`

```py
# Program to plot 2-D Heat map
# using matplotlib.pyplot.imshow() method
import numpy as np
import matplotlib.pyplot as plt

data = np.random.random((12, 12))
plt.imshow(data, cmap='autumn', interpolation='nearest')

plt.title("2-D Heat Map")
plt.show()
```

**输出：**

![](img/daab27ddbe887d73804030660ddd14ee.png)

## 方法二：使用 Seaborn 库

为此，我们使用 `seaborn.heatmap()` 函数。

> **语法：** `seaborn.heatmap(data, *, vmin=None, vmax=None, cmap=None, center=None, robust=False, annot=None, fmt='.2g', annot_kws=None, linewidths=0, linecolor='white', cbar=True, cbar_kws=None, cbar_ax=None, square=False, xticklabels='auto', yticklabels='auto', mask=None, ax=None, **kwargs)`

```py
# Program to plot 2-D Heat map
# using seaborn.heatmap() method
import numpy as np
import seaborn as sns
import matplotlib.pylab as plt

data_set = np.random.rand(10, 10)
ax = sns.heatmap(data_set, linewidth=0.5, cmap='coolwarm')

plt.title("2-D Heat Map")
plt.show()
```

**输出：**

![](img/752130c6f4b6a60478ed0b937a26bdeb.png)

## 方法三：使用 `matplotlib.pyplot.pcolormesh()` 函数

> **语法：** `matplotlib.pyplot.pcolormesh(*args, alpha=None, norm=None, cmap=None, vmin=None, vmax=None, shading='flat', antialiased=False, data=None, **kwargs)`

```py
# Program to plot 2-D Heat map
# using matplotlib.pyplot.pcolormesh() method
import matplotlib.pyplot as plt
import numpy as np

Z = np.random.rand(15, 15)

plt.pcolormesh(Z, cmap='summer')

plt.title('2-D Heat Map')
plt.show()
```

**输出：**

![](img/79ec62fbe80e67e52bbfe366a223963b.png)