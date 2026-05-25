# Python 中的 matplotlib.axes.Axes.get_navigate_mode()

> 原文: [https://www.geeksforgeeks.org/matplotlib-axes-axes-get_navigate_mode-in-python/](https://www.geeksforgeeks.org/matplotlib-axes-axes-get_navigate_mode-in-python/)

`Matplotlib` 是 Python 中的一个库，是 `NumPy` 库的数值-数学扩展。`Axes` 类包含了大部分的图形元素：轴、刻度、`Line2D`、文本、多边形等，并设置坐标系。`Axes` 的实例通过回调属性支持回调。

## matplotlib.axes.Axes.get_navigate_mode() 函数

`matplotlib` 库的 `Axes` 模块中的 `Axes.get_navigate_mode()` 函数用于获取导航工具栏按钮状态：`"PAN"`、`"ZOOM"` 或 `"None"`。

> **语法:** `Axes.get_navigate_mode(self)`
>
> **参数:** 此方法不接受任何参数。
>
> **返回值:** 此方法返回导航模式。

以下示例说明了 `matplotlib.axes.Axes.get_navigate_mode()` 函数在 `matplotlib.axes` 中的使用：

**示例 1:**

```py
# Implementation of matplotlib function
import matplotlib
import matplotlib.pyplot as plt
import numpy as np

t = np.arange(0.0, 2, 0.001)
s = 1 + np.sin(8 * np.pi * t)*0.4

fig, ax = plt.subplots()
ax.plot(t, s)

w = ax.get_navigate_mode()

ax.text(0.5, 1.43, "Navigate Mode : " + str(w),
        fontweight ="bold")

ax.set(xlabel ='X-Axis', ylabel ='Y-Axis',
       xlim =(0, 1.5), ylim =(0.5, 1.5))

ax.set_title('matplotlib.axes.Axes.get_navigate_mode()\
 function Example', fontweight ="bold")

ax.grid()
plt.show()
```

**输出:**
![](img/6d7aeba2e06da00138009672b62b3b99.png)

**示例 2:**

```py
# Implementation of matplotlib function
import numpy as np
import matplotlib.pyplot as plt
np.random.seed(19680801)

fig, ax = plt.subplots()

x, y, s, c = np.random.rand(4, 200)
s *= 200

ax.scatter(x, y, s, c)
ax.set_navigate_mode("ZOOM")
w = ax.get_navigate_mode()

ax.text(0.3, .65, "Navigate Mode : " + str(w),
        fontweight ="bold")

ax.set_title('matplotlib.axes.Axes.get_navigate_mode()\
 function Example', fontweight ="bold")

ax.grid()
plt.show()
```

**输出:**
![](img/e8f03df6456189d65863d723990ee4ce.png)