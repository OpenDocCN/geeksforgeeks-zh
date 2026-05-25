# matplotlib.artist.Artist.remove() 方法详解

> 原文：[https://www.geeksforgeeks.org/matplotlib-artist-artist-remove-in-python/](https://www.geeksforgeeks.org/matplotlib-artist-artist-remove-in-python/)

`【Matplotlib】`是 Python 中的一个库，它是 NumPy 库的数字-数学扩展。`Artist`类包含将渲染到图形画布中的对象的抽象基类。图形中所有可见的元素都是艺术家的子类。

## matplotlib.artist.Artist.remove() 方法

`matplotlib`库的`artist`模块中的`remove()`方法用于在可能的情况下从图形中移除艺术家。

`语法:` `Artist.remove(self)`

`参数:` 此方法不接受任何参数。

`返回:` 此方法返回移除艺术家后的图。

以下示例说明了`matplotlib`中的`matplotlib.artist.Artist.remove()`函数：

**例 1：**

```py
# Implementation of matplotlib function
from matplotlib.artist import Artist
import matplotlib.pyplot as plt

fig, axs = plt.subplots()
axs.plot([1, 2, 3])

# use of remove() method
Artist.remove(axs)

fig.suptitle("""matplotlib.artist.Artist.remove()
function Example""", fontweight="bold")

plt.show()
```

**输出：**

![](img/cef1fde8d05e2868cac333ac98232035.png)

**例 2：**

```py
# Implementation of matplotlib function
from matplotlib.artist import Artist
import matplotlib.pyplot as plt

fig, (axs, axs2) = plt.subplots(2, 1)
gs = axs2.get_gridspec()

# use of remove() method
Artist.remove(axs)

axbig = fig.add_subplot(gs[1:, -1])
axbig.annotate("Removed one Axes",
               (0.4, 0.5),
               xycoords ='axes fraction',
               va ='center')

fig.suptitle("""matplotlib.artist.Artist.remove()
function Example""", fontweight="bold")

plt.show()
```

**输出：**

![](img/099671471d920f419a5d125882279701.png)