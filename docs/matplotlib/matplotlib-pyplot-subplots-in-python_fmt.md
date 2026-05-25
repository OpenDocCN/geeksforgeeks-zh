# matplotlib.pyplot.subplot() 用法详解

> 参考来源：[matplotlib.pyplot.subplot() in Python](https://www.geeksforgeeks.org/matplotlib-pyplot-subplot-in-python/)

**Matplotlib** 是 Python 中的一个库，是 NumPy 库的数值-数学扩展。**Pyplot** 是一个基于状态的接口到 **Matplotlib** 模块，它提供了一个类似于 MATLAB 的接口。

**样本代码**

```py
# sample code
import matplotlib.pyplot as plt

plt.plot([1, 2, 3, 4], [16, 4, 1, 8])
plt.show()
```

**输出:**
![](img/318b2f71555c93680d9f59450380bc8c.png)

## matplotlib.pyplot.subplot() 函数

matplotlib 库 pyplot 模块中的 `subplot()` 函数用于创建一个图形和一组子图。

> **语法:** `matplotlib.pyplot.subplot(nrows=1, ncols=1, sharex=False, sharey=False, squeeze=True, subplot_kw=None, gridspec_kw=None, **fig_kw)`
>
> **参数:** 该方法接受以下描述的参数:
>
> *   `nrows`, `ncols`: 这些参数是子图网格的行数/列数。
> *   `sharex`, `sharey`: 这些参数控制 x (`sharex`) 或 y (`sharey`) 轴之间的属性共享。
> *   `squeeze`: 该参数为可选参数，包含布尔值，默认值为真。
> *   `num`: 此参数是 `pyplot.figure` 关键字，用于设置图形编号或标签。
> *   `subplot_kw`: 此参数是带有传递给 `add_subplot` 调用的关键字的 dict，用于创建每个子图。
> *   `gridspec_kw`: 此参数是带有传递给 `gridspec` 构造函数的关键字的 dict，该构造函数用于创建放置子图的网格。
>
> **返回:** 该方法返回以下值。
>
> *   `Figure`: 此方法返回图布局。
> *   `Axes`: 此方法返回轴对象或轴对象数组。

下面的例子说明了 `matplotlib.pyplot.subplot()` 函数在 `matplotlib.pyplot` 中的作用:

**示例 #1:**

```py
# Implementation of matplotlib function
import numpy as np
import matplotlib.pyplot as plt

# First create some toy data:
x = np.linspace(0, 2 * np.pi, 400)
y = np.sin(x**2)

fig, ax = plt.subplots()
ax.plot(x, y)
ax.set_title('Simple plot')

fig.suptitle('matplotlib.pyplot.subplots() Example')
plt.show()
```

**输出:**
![](img/1d7fe398d580ac924859d8c832d535d6.png)

**示例 #2:**

```py
# Implementation of matplotlib function
import numpy as np
import matplotlib.pyplot as plt

# First create some toy data:
x = np.linspace(0, 1.5 * np.pi, 100)
y = np.sin(x**2)+np.cos(x**2)

fig, axs = plt.subplots(2, 2,
                        subplot_kw = dict(polar = True))
axs[0, 0].plot(x, y)
axs[1, 1].scatter(x, y)

fig.suptitle('matplotlib.pyplot.subplots() Example')
plt.show()
```

**输出:**
![](img/a58695080c1bdb8591ba9891ba6cc374.png)