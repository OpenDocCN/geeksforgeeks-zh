# Matplotlib.pyplot.stem() 在 Python 中的使用

[Matplotlib](https://www.geeksforgeeks.org/graph-plotting-in-python-set-1/) 是 Python 中的可视化库，用于数组的 2D 图。Matplotlib 是一个多平台数据可视化库，构建在 NumPy 数组上，旨在与更广泛的 SciPy 堆栈一起工作。

## `matplotlib.pyplot.stem()`

`matplotlib.pyplot.stem()` 创建茎图。一个 `Stem plot` 在从基线到 y 值的图表下，为每个 x 位置绘制垂直线，并在顶端放置一个标记。

> **语法:** `stem([x,] y, linefmt=None, markerfmt=None, basefmt=None)`
>
> **参数:**
>
> *   `x` (array-like, optional): 茎的 x 位置。默认值: `(0, 1, ..., len(y)-1)`。
> *   `y` (array-like): 茎头的 y 值。
> *   `linefmt` (str, optional): 定义垂直线属性的字符串。通常，这将是一种颜色或颜色加线型：
>     *   `'-'`: 实线
>     *   `'--'`: 虚线
>     *   `'-.'`: 点划线
>     *   `':'`: 点线
>
>     **注意:** 虽然在技术上可以指定除颜色或颜色和线型之外的有效格式（例如 `'rx'` 或 `'-.'`），但这超出了方法的意图，很可能不会产生合理的图。
>
> *   `markerfmt` (str, optional): 定义茎头标记属性的字符串。默认值: `"C0o"`，即以颜色循环的第一种颜色填充的圆圈。
> *   `basefmt` (str, optional): 定义基线属性的格式字符串。
>     **默认:** `"C3-"`（经典模式为 `"C2-"`）。
> *   `bottom` (float, optional, default: 0): 基线的 y 位置。
> *   `label` (str, optional, default: None): 用于图例中茎的标签。
> *   `use_line_collection` (bool, optional, default: False): 如果为 `True`，则将茎线存储并绘制为 `LineCollection`，而不是单个线条。这显著提高了性能，并将成为 Matplotlib 3.3 中的默认选项。如果为 `False`，则默认为使用线性 2D 对象列表的旧行为。
>
> **返回:**
>
> **container**: `StemContainer`
>
> 容器可以被视为一个元组 ( *markerline*, *stemlines*, *baseline* )。

### 示例 #1: 默认图

茎图绘制从基线到 y 坐标的垂直线，并在顶端放置标记。

```py
# importing libraries
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0.1, 2 * np.pi, 41)
y = np.exp(np.sin(x))

plt.stem(x, y, use_line_collection = True)
plt.show()
```

**输出:**
![matplotlib.pyplot.stem()](img/202ded3bb075afbd711a1d6e2c1a13de.png)

### 示例 #2: 自定义格式

基线的位置可以使用 `bottom` 参数进行调整。参数 `linefmt`、`markerfmt` 和 `basefmt` 控制图的基本格式属性。然而，与 `plot` 相反，并非所有属性都可以通过关键字参数进行配置。对于更高级的控制，调整 `pyplot` 返回的线对象。

```py
# importing libraries
import random
import matplotlib.pyplot as plt

x = np.linspace(0.1, 2 * np.pi, 41)
y = np.exp(np.sin(x))

markerline, stemlines, baseline = plt.stem(
    x, y, linefmt ='grey', markerfmt ='D',
    bottom = 1.1, use_line_collection = True)

markerline.set_markerfacecolor('none')
plt.show()
```

**输出:**
![matplotlib.pyplot.stem()](img/e9737c46a87cc451c8e1e7ffc6ef1dec.png)