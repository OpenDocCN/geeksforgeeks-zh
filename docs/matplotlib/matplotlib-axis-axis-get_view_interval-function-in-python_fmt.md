# Matplotlib 中的 axis.get_view_interval() 函数

> 原文: [https://www.geeksforgeeks.org/matplotlib-axis-axis-get_view_interval-function-in-python/](https://www.geeksforgeeks.org/matplotlib-axis-axis-get_view_interval-function-in-python/)

[`Matplotlib`](https://www.geeksforgeeks.org/python-introduction-matplotlib/) 是 Python 中的一个库，是 [`NumPy`](https://www.geeksforgeeks.org/python-introduction-matplotlib/) 库的数值-数学扩展。这是一个神奇的 Python 可视化库，用于 2D 数组图，并用于处理更广泛的 [`SciPy`](https://www.geeksforgeeks.org/python-introduction-matplotlib/) 堆栈。

## `matplotlib.axis.Axis.get_view_interval()` 函数

[`matplotlib`](https://www.geeksforgeeks.org/python-introduction-matplotlib/) 库的 [`Axis`](https://www.geeksforgeeks.org/matplotlib-axis-axis-get_view_interval-function-in-python/) 模块中的 [`Axis.get_view_interval()`](https://www.geeksforgeeks.org/matplotlib-axis-axis-get_view_interval-function-in-python/) 函数用于获取该轴的视图限制（最小，最大）。

**语法:**
```py
axis.get_view_interval(self)
```

**参数:** 该方法不接受任何参数。

**返回值:** 该方法返回该轴的视图限制（最小，最大）。

下面的例子说明了 [`matplotlib.axis.Axis.get_view_interval()`](https://www.geeksforgeeks.org/matplotlib-axis-axis-get_view_interval-function-in-python/) 函数在 [`matplotlib.axis`](https://www.geeksforgeeks.org/matplotlib-axis-axis-get_view_interval-function-in-python/) 中的作用。

### 示例 1

```py
# Implementation of matplotlib function
from matplotlib.axis import Axis
import matplotlib.pyplot as plt
import numpy as np

fig = plt.figure()

x = np.linspace(0,4*np.pi,100)
y = 2*np.sin(x)

ax = fig.add_subplot()
ax.plot(x,y)

print("Value return by get_view_interval() :")
w = ax.xaxis.get_view_interval()
print(w)

ax.grid()

fig.suptitle("""matplotlib.axis.Axis.get_view_interval()
function Example\n""", fontweight ="bold")

plt.show()
```

**输出:**

![](img/33bd1cebd0d819ce3f00cdf9c52077f7.png)

```py
Value return by get_view_interval() :
[-0.62831853 13.19468915]
```

### 示例 2

```py
# Implementation of matplotlib function
from matplotlib.axis import Axis
import matplotlib.pyplot as plt
import numpy as np

np.random.seed(10**7)  
geeks = np.random.randn(40)

fig, ax = plt.subplots()  
ax.acorr(geeks, usevlines = True,  
         normed = True,  
         maxlags = 20, lw = 3)

ax.grid(True)

print("Value return by get_view_interval() :")
w = ax.xaxis.get_view_interval()
print(w)

fig.suptitle("""matplotlib.axis.Axis.get_view_interval()
function Example\n""", fontweight ="bold")

plt.show()
```

**输出:**

![](img/1a6cba4aedba15ad9d2bf51f8b4c76d6.png)

```py
Value return by get_view_interval() :
[-22.  22.]
```