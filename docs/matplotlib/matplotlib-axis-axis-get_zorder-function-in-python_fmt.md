# Python中的matplotlib.axis.Axis.get_zorder()函数

> 原文：[https://www.geeksforgeeks.org/matplotlib-axis-axis-get_zorder-function-in-python/](https://www.geeksforgeeks.org/matplotlib-axis-axis-get_zorder-function-in-python/)

[**Matplotlib**](https://www.geeksforgeeks.org/python-introduction-matplotlib/) 是Python中的一个库，是NumPy库的数值-数学扩展。这是一个神奇的Python可视化库，用于2D数组图，并用于处理更广泛的SciPy堆栈。

## matplotlib.axis.Axis.get_zorder()函数

matplotlib库的`Axis`模块中的`Axis.get_zorder()`函数用于获取艺术家的zorder。

> **语法:** `Axis.get_zorder(self)`
>
> **参数:** 该方法不接受任何参数。
>
> **返回值:** 此方法返回艺术家的zorder。

下面的例子说明了`matplotlib.axis.Axis.get_zorder()`函数在matplotlib.axis中的使用：

### 例 1:

```py
# Implementation of matplotlib function
from matplotlib.axis import Axis
import numpy as np
import matplotlib.pyplot as plt

d = np.arange(49).reshape(7, 7)
xx, yy = np.meshgrid(np.arange(8), np.arange(8))

fig, ax = plt.subplots()

ax.set_aspect(1)
ax.pcolormesh(xx, yy, d)

ax.text(2.4, 6.5, "Zorder Value : "
        + str(Axis.get_zorder(ax)),
        fontweight ="bold")

fig.suptitle('matplotlib.axis.Axis.get_zorder() \
function Example\n', fontweight ="bold")

plt.show()
```

**输出:**

![](img/c38d42a698669e3cd2345889b6bbcf2a.png)

### 例 2:

```py
# Implementation of matplotlib function
from matplotlib.axis import Axis
import numpy as np
import matplotlib.pyplot as plt

xx = np.random.rand(6, 5)

fig, ax = plt.subplots()

ax.pcolor(xx)
ax.set_zorder(-3)

ax.set_title( "Zorder Value : "
        + str(Axis.get_zorder(ax)),
        fontweight ="bold")

fig.suptitle('matplotlib.axis.Axis.get_zorder() \
function Example\n', fontweight ="bold")

plt.show()
```

**输出:**

![](img/abd37baf568870d4872fe8b751291d47.png)