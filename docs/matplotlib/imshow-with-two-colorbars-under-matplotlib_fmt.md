# 在 Matplotlib 下用两个颜色条显示

> 原文: [https://www.geeksforgeeks.org/imshow-with-two-colorbars-under-matplotlib/](https://www.geeksforgeeks.org/imshow-with-two-colorbars-under-matplotlib/)

在本文中，我们将学习如何在 Matplotlib 下使用带有两个颜色条的 `imshow()`。我们来讨论一些概念:

*   `matplotlib` 是一个出色的 Python 可视化库，用于绘制 2D 阵列图。Matplotlib 绘图库是一个基于 NumPy 数组的多平台数据可视化库，旨在与更广泛的 SciPy 堆栈协同工作。它由 John Hunter 于 2002 年推出。
*   可视化最大的好处之一是它允许我们以易于理解的视觉方式直观地访问海量数据。Matplotlib 包含多种图表，如直线图、条形图、散点图、直方图等。
*   Matplotlib 库的 pyplot 模块中的 `imshow()` 函数用于将数据显示为图像；即在 2D 规则网格上。
*   Matplotlib 的 pyplot 模块中的 `colorbar()` 函数向绘图添加颜色条以指示颜色尺度。

## 一个简单的 imshow() 同一个颜色条

```py
# import libraries
import matplotlib.pyplot as plt
import numpy as np

# create image = 10x10 array
img = np.random.randint(-100, 100, (10, 10))

# make plot
fig, ax = plt.subplots()

# show image
shw = ax.imshow(img)

# make bar
bar = plt.colorbar(shw)

# show plot with labels
plt.xlabel('X Label')
plt.ylabel('Y Label')
bar.set_label('ColorBar')
plt.show()
```