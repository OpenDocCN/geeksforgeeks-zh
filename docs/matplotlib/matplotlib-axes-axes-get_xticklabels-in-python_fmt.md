# matplotlib.axes.Axes.get_xticklabels() 用法详解

> 原文链接: https://www.geeksforgeeks.org/matplotlib-axes-get_xticklabels-in-python/

**[Matplotlib](https://www.geeksforgeeks.org/python-introduction-matplotlib/)** 是 Python 中的一个库，是 NumPy 库的数值-数学扩展。`Axes` 类包含了大部分的图形元素：轴、刻度、线、二维文本、多边形等，并设置坐标系。`Axes` 的实例通过回调属性支持回调。

## matplotlib.axes.Axes.get_xticklabels() 函数

`matplotlib` 库的 `Axes` 模块中的 `Axes.get_xticklabels()` 函数用于将 x 刻度标签作为文本实例列表返回。

> **语法:** `Axes.get_xticklabels(self, minor=False, which=None)`
>
> **参数:** 该方法接受以下参数。
>
> *   `minor`: 该参数用于设置主要标签还是次要标签。
> *   `which`: 该参数用于选择返回哪些 ticklabels。
>
> **返回值:** 这个方法返回一个文本实例列表。

下面的例子说明了 `matplotlib.axes.Axes.get_xticklabels()` 函数在 `matplotlib.axes` 中的作用：

### 例 1

```py
# Implementation of matplotlib function
import numpy as np
import matplotlib.pyplot as plt
from matplotlib.patches import Polygon

def func(x):
    return (x - 4) * (x - 6) * (x - 5) + 100

a, b = 2, 9  # integral limits
x = np.linspace(0, 10)
y = func(x)

fig, ax = plt.subplots()
ax.plot(x, y, "k", linewidth = 2)
ax.set_ylim(bottom = 0)

# Make the shaded region
ix = np.linspace(a, b)
iy = func(ix)
verts = [(a, 0), *zip(ix, iy), (b, 0)]
poly = Polygon(verts, facecolor ='green',
               edgecolor ='0.5', alpha = 0.4)
ax.add_patch(poly)

ax.text(0.5 * (a + b), 30,
        r"$\int_a ^ b f(x)\mathrm{d}x$",
        horizontalalignment ='center',
        fontsize = 20)

fig.text(0.9, 0.05, '$x$')
fig.text(0.1, 0.9, '$y$')

ax.spines['right'].set_visible(False)
ax.spines['top'].set_visible(False)

ax.set_xticks((a, b-a, b))
ax.set_xticklabels(('$a$', '$valx$', '$b$'))

w = ax.get_xticklabels()
strr = str(list(w))
ax.text(3.4, 200, "xticklabels values : ",
       fontweight ="bold")
ax.text(1, 185, strr, fontweight ="bold")

fig.suptitle('matplotlib.axes.Axes.get_xticklabels() \
function Example\n\n', fontweight ="bold")
fig.canvas.draw()
plt.show()
```

**输出:**
![](img/4b416275a74be18394686f6a422c42a2.png)

### 例 2

```py
# Implementation of matplotlib function
import numpy as np
import matplotlib.pyplot as plt

# Fixing random state for reproducibility
np.random.seed(19680801)

x = np.linspace(0, 2 * np.pi, 100)
y = np.sin(x)
y2 = y + 0.2 * np.random.normal(size = x.shape)

fig, ax = plt.subplots()
ax.plot(x, y)
ax.plot(x, y2)

ax.set_xticks([0, np.pi, 2 * np.pi])
ax.set_xticklabels(['0', r'$\pi$', r'2$\pi$'])

ax.spines['left'].set_bounds(-1, 1)
ax.spines['right'].set_visible(False)
ax.spines['top'].set_visible(False)

w = ax.get_xticklabels()
strr = str(list(w))
ax.text(2.5, 0, "xticklabels values : ",
        fontweight ="bold")
ax.text(1, -0.2, strr, fontweight ="bold")

fig.suptitle('matplotlib.axes.Axes.get_xticklabels()\
 function Example\n\n', fontweight ="bold")
fig.canvas.draw()
plt.show()
```

**输出:**
![](img/b96209524eaf0a7a379f678e81de8967.png)