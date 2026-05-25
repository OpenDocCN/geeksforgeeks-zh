# Python 中的 Matplotlib.axes.Axes.quiver()

> 原文: [https://www.geeksforgeeks.org/matplotlib-axes-axes-quiver-in-python/](https://www.geeksforgeeks.org/matplotlib-axes-axes-quiver-in-python/)

[Matplotlib](https://www.geeksforgeeks.org/python-introduction-matplotlib/) 是 Python 中的一个库，是 NumPy 库的数值-数学扩展。`Axes` 类包含了大部分的图形元素：轴、刻度、线、二维文本、多边形等，并设置坐标系。`Axes` 的实例通过回调属性支持回调。

## matplotlib.axes.Axes.quiver() 函数

`matplotlib` 库的 `Axes` 模块中的 `Axes.quiver()` 函数也用于绘制箭头的 2D 场。

> **语法:** `Axes.quiver(self, *args, data=None, **kw)`
>
> **参数:** 该方法接受以下描述的参数：
>
> - `X`, `Y`：这些参数是箭头位置的 X 和 Y 坐标。
> - `U`, `V`：这些参数是箭头向量的 x 和 y 分量。
> - `C`：该参数包含通过 `norm` 和 `cmap` 通过颜色映射定义箭头颜色的数字数据。
> - `pivot`：此参数是箭头锚定到 `X`, `Y` 网格的部分。
> - `units`：此参数为箭头尺寸（长度除外）以该单位的倍数测量。
> - `angles`：该参数是确定箭头角度的方法。
> - `scale`：此参数为每个箭头长度单位的数据单位数。
> - `scale_units`：此参数为可选参数，它包含以下值 *‘width’, ‘height’, ‘points’, ‘inches’, ‘x’, ‘y’, ‘xy’*。
> - `width`：此参数为轴宽，单位为箭头。
> - `headwidth`：该参数为轴宽倍数的头部宽度。
> - `headlength`：该参数为轴宽倍数的长宽。
> - `headaxislength`：该参数为轴宽倍数的头部宽度。
> - `minshaft`：该参数为轴交点处的轴头长度。
> - `minlength`：该参数是轴宽倍数的最小长度。
> - `color`：该参数是箭头的显式颜色。

以下示例说明了 `matplotlib.axes.Axes.quiver()` 函数在 `matplotlib.axes` 中的作用：

### 例 1:

```python
# Implementation of matplotlib function
import matplotlib.pyplot as plt
import numpy as np

X = np.arange(-20, 20, 0.5)
Y = np.arange(-20, 20, 0.5)
U, V = np.meshgrid(X, Y)

fig, ax = plt.subplots()
q = ax.quiver(X, Y, U, V)

ax.set_title('matplotlib.axes.Axes.quiver()\
 Example', fontsize = 14, fontweight ='bold')
plt.show()
```

**输出:**
![](img/5c872b95f03133110ad6e797b9b78e7d.png)

### 例 2:

```python
# Implementation of matplotlib function
import matplotlib.pyplot as plt
import numpy as np

X, Y = np.meshgrid(np.arange(0, 2 * np.pi, .2),
                   np.arange(0, 2 * np.pi, .2))
U = np.cos(X**2)
V = np.sin(Y**2)
C = U**2 + V**2

fig, ax = plt.subplots()
ax.quiver(X, Y, U, V, C, units ='width')
ax.set_title('matplotlib.axes.Axes.quiver() \
Example', fontsize = 14, fontweight ='bold')
plt.show()
```

**输出:**
![](img/2ea475393018c71705909d76058c1cd6.png)