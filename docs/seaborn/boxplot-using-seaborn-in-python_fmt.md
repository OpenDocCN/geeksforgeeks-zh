# 使用 Python 中的 Seaborn 绘制箱线图

> 原文：[https://www.geeksforgeeks.org/boxplot-using-seaborn-in-python/](https://www.geeksforgeeks.org/boxplot-using-seaborn-in-python/)

Seaborn 是一个用 Python 绘制统计图形的惊人可视化库。它提供了漂亮的默认样式和调色板，使统计图更有吸引力。它建立在 `matplotlib` 库的顶部，也与 `pandas` 的数据结构紧密结合。

## 箱线图

箱线图有助于保持定量数据的分布，便于变量之间或分类变量之间的比较。显示四分位数和中位数置信区间（如果启用）的箱线图主体。中线在每个方框的中线处有水平线，而胡须的垂直线延伸到最末端，非异常数据点和帽是胡须末端的水平线。

> **语法：** `seaborn.boxplot(x=None, y=None, hue=None, data=None, order=None, hue_order=None, orient=None, color=None, palette=None, saturation=0.75, width=0.8, dodge=True, fliersize=5, linewidth=None, whis=1.5, ax=None, **kwargs)`
>
> **参数：**
> `x`，`y`，`hue`：用于绘制长格式数据的输入。
> `data`：用于绘图的数据集。如果 `x` 和 `y` 不存在，这被解释为宽形。
> `color`：所有元素的颜色。
>
> **返回：** 返回绘制了绘图的坐标轴对象。

**示例 1：** 使用 `violinplot()` 对 “fmri” 数据集进行基本可视化

## Python 3

```py
import seaborn

seaborn.set(style='whitegrid')
fmri = seaborn.load_dataset("fmri")

seaborn.boxplot(x="timepoint",
                y="signal",
                data=fmri)
```

**输出：**

![](img/2eaa3f6e86eba3ca8698df04e442c86f.png)

**示例 2：** 使用 `boxplot()` 对 “tips” 数据集进行基本可视化

## Python 3

```py
import seaborn

seaborn.set(style='whitegrid')
tip = seaborn.load_dataset('tips')

seaborn.boxplot(x='day', y='tip', data=tip)
```