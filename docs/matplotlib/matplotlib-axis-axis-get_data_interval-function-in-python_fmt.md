# matplotlib.axis.Axis.get_data_interval()函数

> 原文：[https://www.geeksforgeeks.org/matplotlib-axis-axis-get_data_interval-function-in-python/](https://www.geeksforgeeks.org/matplotlib-axis-axis-get_data_interval-function-in-python/)

`Matplotlib`是Python中的一个库，是`NumPy`库的数值-数学扩展。这是一个神奇的Python可视化库，用于2D数组图，并用于处理更广泛的`SciPy`堆栈。

## 函数介绍

`matplotlib`库的`Axis`模块中的`Axis.get_data_interval()`函数用于获取该轴数据限制的`interval`实例。

> **语法:** `axis.get_data_interval(self)`
>
> **参数:** 该方法不接受任何参数。
>
> **返回值:** 该方法返回该轴数据限制的区间实例。

下面的例子说明了`matplotlib.axis.Axis.get_data_interval()`函数在`matplotlib.axis`中的作用。

### 例1

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

print("Value return by get_data_interval() :")
w = ax.xaxis.get_data_interval()
print(w)

ax.grid()

fig.suptitle("""matplotlib.axis.Axis.get_data_interval()
function Example\n""", fontweight ="bold")

plt.show()
```

**输出:**

![](img/ef86d3d5e1970dfdddeaa45ae808cd1d.png)

```py
Value return by get_data_interval() :
[ 0.         12.56637061]
```

### 例2

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

print("Value return by get_data_interval() :")
w = ax.xaxis.get_data_interval()
print(w)

fig.suptitle("""matplotlib.axis.Axis.get_data_interval()
function Example\n""", fontweight ="bold")

plt.show()
```

**输出:**

![](img/a6b54d0955ca92606d21ab9a93d6abf0.png)

```py
Value return by get_data_interval() :
[-20.  20.]
```