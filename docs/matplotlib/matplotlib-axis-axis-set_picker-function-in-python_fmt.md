# matplotlib.axis.Axis.set_picker()函数

> 原文: [https://www.geeksforgeeks.org/matplotlib-axis-axis-set_picker-function-in-python/](https://www.geeksforgeeks.org/matplotlib-axis-axis-set_picker-function-in-python/)

[**Matplotlib**](https://www.geeksforgeeks.org/python-introduction-matplotlib/) 是 Python 中的一个库，是 NumPy 库的数值-数学扩展。这是一个神奇的 Python 可视化库，用于 2D 数组图，并用于处理更广泛的 SciPy 堆栈。

`matplotlib.axis.Axis.set_picker()` 函数是 `matplotlib` 库的 `Axis` 模块中的一个函数，用于定义艺术家的拾取行为。

> **语法:** `Axis.set_picker(self, picker)`
>
> **参数:** 该方法接受以下参数。
>
> *   `picker`: 此参数用于设置拾取行为。这可以是 `None`、`bool`、`float` 或 `callable`。
>
> **返回值:** 此方法返回艺术家的拾取行为。

下面的例子说明了 `matplotlib.axis.Axis.set_picker()` 函数在 `matplotlib.axis` 中的作用:

### 示例 1

```py
# Implementation of matplotlib function
from matplotlib.axis import Axis
import numpy as np
import matplotlib.pyplot as plt

np.random.seed(19680801)

volume = np.random.rayleigh(27, size = 40)
amount = np.random.poisson(7, size = 40)
ranking = np.random.normal(size = 40)
price = np.random.uniform(1, 7, size = 40)

fig, ax = plt.subplots()

scatter = ax.scatter(volume * 2,
                     amount**3,
                     c = ranking**3,
                     s = price**3,
                     vmin = -3,
                     vmax = 3,
                     cmap ="Spectral")

Axis.set_picker(ax, picker = 4)

fig.suptitle('matplotlib.axis.Axis.set_picker() \
function Example\n', fontweight ="bold")

plt.show()
```

**输出:**

![](img/f9147ede6d199a62298422477e285712.png)

### 示例 2

```py
# Implementation of matplotlib function
from matplotlib.axis import Axis
import numpy as np
import matplotlib.pyplot as plt

X = np.random.rand(10, 200)
xs = np.mean(X, axis = 1)
ys = np.std(X, axis = 1)

fig = plt.figure()
ax = fig.add_subplot(111)
line, = ax.plot(xs, ys, 'go-')

Axis.set_picker(ax, picker = True)

fig.suptitle('matplotlib.axis.Axis.set_picker() \
function Example\n', fontweight ="bold")

plt.show()
```

**输出:**

![](img/e5d8b3155f7b55d944293d5768047431.png)