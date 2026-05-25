# Matplotlib Axes.bxp() 函数详解

> 原文链接：[https://www.geeksforgeeks.org/matplotlib-axes-bxp-in-python/](https://www.geeksforgeeks.org/matplotlib-axes-bxp-in-python/)

`Matplotlib` 是 Python 中的一个库，是 NumPy 库的数值-数学扩展。`Axes` 类包含了大部分的图形元素：轴、刻度、`Line2D`、文本、多边形等，并设置坐标系。`Axes` 的实例通过回调属性支持回调。

## matplotlib.axes.Axes.bxp() 函数

`matplotlib` 库的 `Axes` 模块中的 `Axes.bxp()` 函数用于对 `x` 的每一列或序列 `x` 中的每一个向量做一个箱线图。

**语法：**
```python
Axes.bxp(self, bxpstats, positions=None, widths=None, vert=True, patch_artist=False, shownotches=False, showmeans=False, showcaps=True, showbox=True, showfliers=True, boxprops=None, whiskerprops=None, medianprops=None, capprops=None, meanprops=None, meanline=False, manage_ticks=True, zorder=None)
```

**参数：** 该方法接受以下描述的参数：

*   `bxpstats`： 此参数是包含每个箱线图统计信息的字典列表。
*   `positions`： 该参数用于设置箱线图的位置。
*   `vert`： 该参数为可选参数，包含布尔值。如果为 `True` 则绘制垂直箱线图，否则为水平。
*   `widths`： 此参数用于用标量或序列设置每个箱线图的宽度。
*   `patch_artist`： 如果该参数为 `False`，则使用 `Line2D` artist 生成箱子。否则，使用带有 `Patch` artist 的箱子。
*   `manage_ticks`： 此参数用于调整刻度位置和标签。
*   `zorder`： 该参数用于设置箱线图的 `zorder`。
*   `shownotches`： 该参数包含布尔值。它被用来绘制带缺口的箱线图。
*   `showmeans`： 该参数包含布尔值。它用于切换均值的显示。
*   `showcaps`： 此参数包含布尔值。它用于切换箱须顶端横杠的显示。
*   `showfliers`： 此参数包含布尔值。它用于切换离群点的显示。
*   `boxprops`： 该参数用于设置箱体的绘图风格。
*   `whiskerprops`： 该参数用于设置箱须的绘制风格。
*   `capprops`： 该参数用于设置箱须顶端横杠的绘制样式。
*   `flierprops`： 此参数用于设置离群点的绘制样式。
*   `medianprops`： 此参数用于设置中位数线的绘制方式。
*   `meanprops`： 此参数用于设置均值的绘制风格。

**返回：** 这将返回一个字典，将箱线图的每个组件映射到 `matplotlib.line.Line2D` 实例的列表。

下面的例子说明了 `matplotlib.axes.Axes.bxp()` 函数在 `matplotlib.axes` 中的作用：

**示例 1：**

```python
import numpy as np
import matplotlib.pyplot as plt
import matplotlib.cbook as cbook

np.random.seed(10**7)
data = np.random.lognormal(size=(10, 4),
                           mean=4.5,
                           sigma=4.75)

labels = ['G1', 'G2', 'G3', 'G4']

result = cbook.boxplot_stats(data,
                             labels=labels,
                             bootstrap=1000)

for n in range(len(result)):
    result[n]['med'] = np.median(data)
    result[n]['mean'] *= 0.1

fig, axes1 = plt.subplots()
axes1.bxp(result)

axes1.set_title('matplotlib.axes.Axes.bxp() Example')
plt.show()
```

**输出：**
![](img/08cb732857d69e216c9beecf49a848cd.png)

**示例 2：**

```python
import numpy as np
import matplotlib.pyplot as plt
import matplotlib.cbook as cbook

np.random.seed(10**7)
data = np.random.lognormal(size=(37, 4),
                           mean=4.5,
                           sigma=1.75)
labels = ['G1', 'G2', 'G3', 'G4']

stats = cbook.boxplot_stats(data, labels=labels,
                            bootstrap=100)

for n in range(len(stats)):
    stats[n]['med'] = np.median(data)
    stats[n]['mean'] *= 2

fig, [axes1, axes2, axes3] = plt.subplots(nrows=1,
                                          ncols=3,
                                          sharey=True)

axes1.bxp(stats)
axes2.bxp(stats, showmeans=True)
axes3.bxp(stats, showmeans=True, meanline=True)

axes2.set_title('matplotlib.axes.Axes.bxp() Example')
plt.show()
```

**输出：**
![](img/87fe53d5cbf3f4573a2553852d15ed39.png)