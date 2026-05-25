# matplotlib.axes.acorr()函数详解

> 原文链接: https://www.geeksforgeeks.org/matplotlib-axes-acorr-in-python/

**[Matplotlib](https://www.geeksforgeeks.org/python-introduction-matplotlib/)** 是Python中的一个库，是NumPy库的数值-数学扩展。`Axes`类包含了大部分的图形元素：轴、刻度、Line2D、文本、多边形等，并设置坐标系。`Axes`的实例通过回调属性支持回调。

## 函数描述

`matplotlib`库的`Axes`模块中的`Axes.acorr()`函数用于绘制`x`的自相关。

## 语法

```py
Axes.acorr(self, x, *, data=None, **kwargs)
```

## 参数

该方法接受以下参数：

*   `x`：标量序列。
*   `detrend`：可选参数。默认值为`mlab.detrend_none`。
*   `normed`：可选参数，布尔值。默认值为`True`。
*   `usevlines`：可选参数，布尔值。默认值为`True`。
*   `maxlags`：可选参数，整数值。默认值为`10`。
*   `linestyle`：可选参数，用于绘制数据点，仅当`usevlines`为`False`时使用。
*   `marker`：可选参数，字符串。

## 返回值

该方法返回以下内容：

*   `lags`：滞后向量。
*   `c`：自相关向量。
*   `lines`：`LineCollection`如果`usevlines`为`True`，否则为`Line2D`。
*   `b`：如果`usevlines`为`True`，则返回0处的水平线，否则返回`None`。

结果是`(lags, c, lines, b)`。

## 示例

下面的例子说明了`matplotlib.axes.Axes.acorr()`函数的作用：

### 示例 1

```py
# Implementation of matplotlib function

import matplotlib.pyplot as plt
import numpy as np

# Time series data
geeks = np.array([24.40, 110.25, 20.05,
                  22.00, 61.90, 7.80, 
                  15.00, 22.80, 34.90, 
                  57.30])

# Plot autocorrelation
fig, ax = plt.subplots()
ax.acorr(geeks, maxlags = 9)

# Add labels to autocorrelation plot
ax.set_xlabel('X-axis')
ax.set_ylabel('Y-axis')

ax.set_title('matplotlib.axes.Axes.acorr() Example')

plt.show()
```

**输出:**
![](img/1fcf4ff9014103fbb4a2aaf9287533ca.png)

### 示例 2

```py
# Implementation of matplotlib function
import matplotlib.pyplot as plt
import numpy as np

# Fixing random state for reproducibility
np.random.seed(10**7)
geeks = np.random.randn(100)

fig, ax = plt.subplots()
ax.acorr(geeks, usevlines = True, normed = True,
         maxlags = 80, lw = 3)
ax.grid(True)

ax.set_title('matplotlib.axes.Axes.acorr() Example')

plt.show()
```

**输出:**
![](img/c9e42bfb5a92e2a317272e925ecc66d1.png)