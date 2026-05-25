# Matplotlib 中的 ArrowStyle 类

> 原文：[https://www.geeksforgeeks.org/matplotlib-patches-arrowstyle-class-in-python/](https://www.geeksforgeeks.org/matplotlib-patches-arrowstyle-class-in-python/)

**[Matplotlib](https://www.geeksforgeeks.org/python-matplotlib-an-overview/)** 是 Python 中一个惊人的可视化库，用于数组的 2D 图。Matplotlib 是一个多平台数据可视化库，构建在 NumPy 数组上，旨在与更广泛的 SciPy 堆栈一起工作。

## matplotlib.patches.ArrowStyle

`matplotlib.patches.ArrowStyle` 类是一个容器类，它定义了许多箭头样式的类，用于沿着提供的路径创建箭头路径。这些主要用于 `FancyArrowPatch`。

### 语法

```python
class matplotlib.patches.ArrowStyle
```

以下子类是为各种箭头样式定义的：

| 类名 | 名称 | 属性 |
| :--- | :--- | :--- |
| `Curve` | `-` | 无 |
| `Curve` | `->` | head_length=0.4, head_width=0.2 |
| `Bracket` | `-[` | widthB=1.0, lengthB=0.2, angleB=None |
| `CurveFilledB` | `-|>` | head_length=0.4, head_width=0.2 |
| `CurveFilledA` | `<|-` | head_length=0.4, head_width=0.2 |
| `CurveFilledAB` | `<|->` | head_length=0.4, head_width=0.2 |
| `CurveB` | `]-` | widthA=1.0, lengthA=0.2, angleA=None |
| `CurveAB` | `]-[` | widthA=1.0, lengthA=0.2, angleA=None, widthB=1.0, lengthB=0.2, angleB=None |
| `Wedge` | `wedge` | head_length=0.4, head_width=0.4, tail_width=0.4 |
| `Simple` | `simple` | head_length=0.5, head_width=0.5, tail_width=0.2 |
| `Fancy` | `fancy` | head_length=0.4, head_width=0.4, tail_width=0.4 |
| `BarAB` | `|-|` | widthA=1.0, angleA=None, widthB=1.0, angleB=None |

### 例 1

```python
import matplotlib.pyplot as plt
from matplotlib.patches import ArrowStyle

plt.figure(1, figsize=(9, 9))

ArrowStyle("Wedge")

ax = plt.subplot(111)

ax.annotate("",
            xy=(0.2, 0.2), xycoords='data',
            xytext=(0.8, 0.8), textcoords='data',
            arrowprops=dict(arrowstyle="Wedge",
                            connectionstyle="arc3"),
            )

plt.show()
```

**输出：**
![](img/99e71249ed8dbde98d0e0e5ccc843924.png)

### 例 2

```python
import matplotlib.patches as mpatch
import matplotlib.pyplot as plt

figheight = 8
fig = plt.figure(figsize=(9, figheight), dpi=80)
fontsize = 0.4 * fig.dpi

def make_boxstyles(ax):
    styles = mpatch.BoxStyle.get_styles()

    for i, (stylename, styleclass) in enumerate(sorted(styles.items())):
        ax.text(0.5,
                (float(len(styles)) - 0.5 - i)/len(styles),
                stylename,
                ha="center",
                size=fontsize,
                transform=ax.transAxes,
                bbox=dict(boxstyle=stylename,
                          fc="g", ec="r"))

def make_arrowstyles(ax):
    styles = mpatch.ArrowStyle.get_styles()

    ax.set_xlim(0, 4)
    ax.set_ylim(0, figheight)

    for i, (stylename, styleclass) in enumerate(sorted(styles.items())):
        y = (float(len(styles)) - 0.25 - i) / len(styles) * figheight
        p = mpatch.Circle((3.2, y), 0.2, fc="r")
        ax.add_patch(p)

        ax.annotate(stylename, (3.2, y),
                    (2., y),
                    ha="right", va="center",
                    size=fontsize,
                    arrowprops=dict(arrowstyle=stylename,
                                    patchB=p,
                                    shrinkA=5,
                                    shrinkB=5,
                                    fc="w", ec="r",
                                    connectionstyle="arc3, rad=-0.05",
                                    ),
                    bbox=dict(boxstyle="square", fc="g"))

    ax.xaxis.set_visible(False)
    ax.yaxis.set_visible(False)

ax1 = fig.add_subplot(121, frameon=False, xticks=[], yticks=[])
make_boxstyles(ax1)

ax2 = fig.add_subplot(122, frameon=False, xticks=[], yticks=[])
make_arrowstyles(ax2)

plt.show()
```

**输出：**
![](img/40837649dfe81f75bb050e792fa17cc9.png)