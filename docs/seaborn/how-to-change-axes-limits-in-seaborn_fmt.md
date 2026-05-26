# 如何在 Seaborn 中更改轴限制？

> 原文: [https://www.geeksforgeeks.org/how-to-change-axes-limits-in-seaborn/](https://www.geeksforgeeks.org/how-to-change-axes-limits-in-seaborn/)

[Seaborn](https://www.geeksforgeeks.org/python-seaborn-tutorial/) 是基于 [matplotlib](https://www.geeksforgeeks.org/matplotlib-tutorial/) 的 Python 数据可视化库。它提供了一个高级界面，用于绘制吸引人且信息丰富的统计图形。`Axes` 类包含了大部分的图形元素：轴、刻度、线 2D、文本、多边形等，并设置坐标系。在 `Axes` 模块中有两种方法可用于改变限制：

1.  [`matplotlib.axes.Axes.set_xlim()`](https://www.geeksforgeeks.org/matplotlib-axes-axes-set_xlim-in-python/)：matplotlib 库的 `Axes` 模块用于设置 x 轴视图限制。
2.  [`matplotlib.axes.Axes.set_ylim()`](https://www.geeksforgeeks.org/matplotlib-axes-axes-set_ylim-in-python/)：matplotlib 库的 `Axes` 模块用于设置 y 轴视图限制。

**语法:**

```py
Axes.set_xlim(self, left=None, right=None, emit=True, auto=False, *, xmin=None, xmax=None)
Axes.set_ylim(self, bottom=None, top=None, emit=True, auto=False, *, ymin=None, ymax=None)
```

**参数:**

*   `bottom`：此参数是数据坐标中的底部 xlim/ylim。
*   `top`：此参数是数据坐标中的顶级 xlim/ylim。
*   `emit`：该参数用于通知观察者极限变化。
*   `auto`：此参数用于打开 x 轴/y 轴的自动缩放。
*   `xmin`、`xmax`、`ymin`、`ymax`：这些参数等同于 `bottom` 和 `top`，同时传递 `xmin`/`ymin` 和 `bottom` 或 `xmax`/`ymax` 和 `top` 是错误的。

**返回:**

`bottom`，`top`：这将返回数据坐标中新的 x 轴/y 轴限制。

## 例 1

```py
# Import module
import matplotlib.pyplot as plt
import seaborn as sns

# assign data
data = [3, 7, 9, 11, 12, 14,
        15, 16, 18, 19, 20,
        23, 25, 28]

# depict visualization
fig, ax = plt.subplots()
sns.distplot(data, ax=ax)
ax.set_xlim(1, 70)
plt.show()
```

**输出:**

![](img/5e5684da2423e1e9583b48d19d512ede.png)

## 例 2

```py
# import module
import seaborn as sns
sns.set_style("whitegrid")

# assign dataset
tips = sns.load_dataset("tips")

# depict visualization
gfg = sns.boxplot(x="day", y="total_bill",
                  data=tips)
gfg.set_ylim(0, 80)
```

**输出:**

![](img/d2be583870fd256a6486b7cbac1687b8.png)