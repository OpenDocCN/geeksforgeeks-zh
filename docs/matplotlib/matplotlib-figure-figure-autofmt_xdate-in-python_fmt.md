# matplotlib.figure.Figure.autofmt_xdate()函数详解

> 原文链接：[https://www.geeksforgeeks.org/matplotlib-figure-automt_xdate-in-python/](https://www.geeksforgeeks.org/matplotlib-figure-automt_xdate-in-python/)

`Matplotlib`是Python中的一个库，是NumPy库的数值数学扩展。`Figure`模块提供了顶级的艺术家`Figure`，包含了所有的绘图元素。该模块用于控制所有绘图元素的子图和顶层容器的默认间距。

## `matplotlib.figure.Figure.autofmt_xdate()`函数

利用`matplotlib`库的`autofmt_xdate()`方法对图形模块中的日期标签进行旋转和右对齐。

> **语法:** `autofmt_xdate(self, bottom=0.2, rotation=30, ha='right', which=None)`
>
> **参数:** 这接受下面描述的以下参数:
>
> *   `bottom`: 该参数为`subplots_adjust()`的子图底部边距。
> *   `rotation`: 该参数是x轴刻度标签的旋转角度。
> *   `ha`: 此参数是x轴刻度标签的水平对齐方式。
> *   `which`: 该参数选择旋转哪些标签。
>
> **返回:** 该方法不返回值。

下面的例子说明了`matplotlib.figure.Figure.autofmt_xdate()`函数在`matplotlib.figure`中的作用:

**例 1:**

```py
# Implementation of matplotlib function
import numpy as np
import matplotlib.pyplot as plt
import matplotlib.dates as mdates
import matplotlib.cbook as cbook

years = mdates.YearLocator()   
months = mdates.MonthLocator()  
years_fmt = mdates.DateFormatter('%Y')

with cbook.get_sample_data('goog.npz') as datafile:
    data = np.load(datafile)['price_data'].view(np.recarray)

fig, ax = plt.subplots()
ax.plot('date', 'adj_close', 
         data = data[:300],
         color ="green")

ax.xaxis.set_major_locator(years) 
ax.format_ydata = lambda x: '$%1.2f' % x
ax.grid(True)

fig.autofmt_xdate()

fig.suptitle('matplotlib.figure.Figure.autofmt_xdate() \
function Example\n\n', fontweight ="bold")

plt.show()
```

**输出:**
![](img/0020a88551a65175bcad291379613e4e.png)

**例 2:**

```py
# Implementation of matplotlib function
import datetime
import matplotlib.pyplot as plt
from matplotlib.dates import DayLocator, HourLocator, DateFormatter, drange
import numpy as np

date1 = datetime.datetime(2020, 4, 2)
date2 = datetime.datetime(2020, 4, 6)
delta = datetime.timedelta(hours = 6)
dates = drange(date1, date2, delta)

y = np.arange(len(dates))

fig, ax = plt.subplots()
ax.plot_date(dates, y ** 2, 'g')

ax.set_xlim(dates[0], dates[-1])

ax.xaxis.set_major_locator(DayLocator())
ax.xaxis.set_minor_locator(HourLocator(range(0, 25, 6)))
ax.xaxis.set_major_formatter(DateFormatter('%Y-%m-%d'))

ax.fmt_xdata = DateFormatter('%Y-%m-%d %H:%M:%S')
fig.autofmt_xdate()

fig.suptitle('matplotlib.figure.Figure.autofmt_xdate() \
function Example\n\n', fontweight ="bold")

plt.show()
```

**输出:**
![](img/40454f14ade8e22e0a57b4a48103a1bd.png)