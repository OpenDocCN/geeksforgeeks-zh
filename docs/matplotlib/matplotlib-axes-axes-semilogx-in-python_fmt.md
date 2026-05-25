# matplotlib.axes.semilogx() 用法详解

## 表示

> 原文链接: [https://www.geeksforgeeks.org/matplotlib-axes-semilogx-in-python/](https://www.geeksforgeeks.org/matplotlib-axes-semilogx-in-python/)

**[Matplotlib](https://www.geeksforgeeks.org/python-introduction-matplotlib/)** 是 Python 中的一个库，是 NumPy 库的数值-数学扩展。`Axes` 类包含了大部分的图形元素：轴、刻度、线（2D）、文本、多边形等，并设置坐标系。`Axes` 的实例通过回调属性支持回调。

## matplotlib.axes.Axes.semilogx() 函数

`matplotlib` 库的 `Axes` 模块中的 `axes.semilogx()` 函数用于在 x 轴上进行对数缩放的绘图。

**语法:**
```py
Axes.semilogx(self, *args, **kwargs)
```

**参数:** 该方法接受以下描述的参数:
*   `basex`: 此参数是 x 对数的底数，可以选择，默认值为 `10`。
*   `subx`: 此参数是次要 x 刻度的位置序列，是可选的。
*   `nonposx`: 此参数是 x 中的非正值，可被屏蔽为无效，或被裁剪为非常小的正数。

**返回:** 这将返回以下内容:
*   `lines`: 这将返回表示打印数据的线（2D）对象列表。

下面的例子说明了 `matplotlib.axes.Axes.semilogx()` 函数在 `matplotlib.axes` 中的作用:

## 示例-1

```py
# Implementation of matplotlib function

import numpy as np
import matplotlib.pyplot as plt

fig, ax = plt.subplots()

dt = 0.1
test = np.arange(dt, 30.0, dt)

ax.semilogx(test, np.exp(-test / 6.0))
ax.grid()

ax.set_title('matplotlib.axes.Axes.semilogx Example1')
plt.show()
```

**输出:**
![](img/d7ff061e5bac53e7a22cbc381b10a5ba.png)

## 示例-2

```py
# Implementation of matplotlib function

import numpy as np
import matplotlib.pyplot as plt

test = np.arange(0.01, 30.0, 0.1)

# Create figure
fig, ax = plt.subplots()

# log x axis
ax.semilogx(test, np.sin(3 * np.pi * test))
ax.grid()

ax.set_title('matplotlib.axes.Axes.semilogx Example2')
plt.show()
```

**输出:**
![](img/5b784896184e78511b7e2d4c79e9981d.png)