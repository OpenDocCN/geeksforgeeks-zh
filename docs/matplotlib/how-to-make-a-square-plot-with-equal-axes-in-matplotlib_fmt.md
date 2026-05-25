# 如何在 Matplotlib 中制作等轴方形图？

> 原文: [https://www.geeksforgeeks.org/how-to-make-a-square-plot-with-equal-axes-in-matplotlib/](https://www.geeksforgeeks.org/how-to-make-a-square-plot-with-equal-axes-in-matplotlib/)

在本文中，我们将讨论如何使用 [`matplotlib`](https://www.geeksforgeeks.org/python-introduction-matplotlib/) 模块来说明等轴正方形图。我们可以使用 [`matplotlib.axes.axes.set_aspect()`](https://www.geeksforgeeks.org/matplotlib-axes-axes-set_aspect-in-python/) 和 [`matplotlib.pyplot.axis()`](https://www.geeksforgeeks.org/matplotlib-pyplot-axis-in-python/) 的方法来描绘一个方形图。

## 使用 `set_aspect()` 方法

> **语法:** `matplotlib.axes.set_aspect()`
>
> **参数:**
>
> - **aspect:** 此参数接受以下值 {'auto', 'equal'} 或 num。
> - **adjustable:** 这定义了将调整哪个参数以满足所需的方面。
> - **anchor:** 此参数用于定义如果由于方面限制而有额外空间，轴将绘制在哪里。
> - **share:** 此参数用于将设置应用于所有共享轴。

### 例 1

我们可以使用 `matplotlib.axes.axes.set_aspect()` 方法生成一个方形图。我们将分配 `'equal'` 作为 `aspect` 参数，`'box'` 作为 `adjustable` 参数。

```python
# import required modules
import numpy as np
import matplotlib.pyplot as plt

# adjust coordinates
x = y = [i for i in range(0, 6)]

# depict illustration
fig = plt.figure()
ax = fig.add_subplot()
plt.plot(x, y)

# square plot
ax.set_aspect('equal', adjustable='box')
plt.show()
```

**输出:**

![](img/5f77f640b71f47f78677cf78ccb6e2e4.png)

### 例 2

当两个坐标轴的范围相等时，上面的例子可能会产生一个方形图。为了在任何情况下都生成方形图，我们需要使用额外的设置来调整视图比例：

```python
ax.set_aspect(1.0 / ax.get_data_ratio(), adjustable='box')
```

```python
# import required modules
import numpy as np
import matplotlib.pyplot as plt

# adjust coordinates
x = y = [i for i in range(0, 6)]

# depict illustration
fig = plt.figure()
ax = fig.add_subplot()
plt.plot(x, y)

# square plot
ax.set_aspect(1.0 / ax.get_data_ratio(), adjustable='box')
plt.show()
```