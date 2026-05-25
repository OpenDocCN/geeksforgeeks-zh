# Python中的matplotlib.dates.epoch2num()

> 原文：[https://www.geeksforgeeks.org/matplotlib-dates-epoch2num-in-python/](https://www.geeksforgeeks.org/matplotlib-dates-epoch2num-in-python/)

[Matplotlib](https://www.geeksforgeeks.org/python-matplotlib-an-overview/) 是Python中一个惊人的可视化库，用于数组的2D图。Matplotlib是一个多平台数据可视化库，构建在NumPy数组上，旨在与更广泛的SciPy堆栈一起工作。

## matplotlib.dates.epoch2num()

`matplotlib.dates.epoch2num()`功能用于从0001开始将一个纪元或一系列纪元转换为新的日期格式。

> **语法：** `matplotlib.dates.epoch2num(e)`
> 
> **参数：**
> 
> *   `e`：可以是一个纪元，也可以是一系列纪元。
> 
> **返回：** 从0001日开始的新日期格式。

**例1：**

```py
import random
import matplotlib.pyplot as plt
import matplotlib.dates as mdates

# generate some random data
# for approx 5 yrs
random_data = [float(random.randint(1487517521,
                                    14213254713))
               for _ in range(1000)]

# convert the epoch format to
# matplotlib date format 
mpl_data = mdates.epoch2num(random_data)

# plotting the graph
fig, axes = plt.subplots(1, 1)
axes.hist(mpl_data, bins = 51, color ='green')
locator = mdates.AutoDateLocator()

axes.xaxis.set_major_locator(locator)
axes.xaxis.set_major_formatter(mdates.AutoDateFormatter(locator))

plt.show()
```

**输出：**
![](img/90e56fbb04a009e37f57716bab2ad4f7.png)

**例2：**

```py
from tkinter import *
from tkinter import ttk
import time 
import matplotlib
import queue
from matplotlib.backends.backend_tkagg import FigureCanvasTkAgg, NavigationToolbar2Tk
from matplotlib.figure import Figure
import matplotlib.animation as animation
import matplotlib.dates as mdate

root = Tk()

graphXData = queue.Queue()
graphYData = queue.Queue()

def animate(objData):

    line.set_data(list(graphXData.queue), 
                  list(graphYData.queue))

    axes.relim()
    axes.autoscale_view()

figure = Figure(figsize =(5, 5), dpi = 100)
axes = figure.add_subplot(111)
axes.xaxis_date()

line, = axes.plot([], [])
axes.xaxis.set_major_formatter(mdate.DateFormatter('%H:%M'))

canvas = FigureCanvasTkAgg(figure, root)
canvas.get_tk_widget().pack(side = BOTTOM, 
                            fill = BOTH, 
                            expand = True)

for cnt in range (600):

    graphXData.put(matplotlib.dates.epoch2num(time.time()-(600-cnt)))
    graphYData.put(0)

ani = animation.FuncAnimation(figure, animate, interval = 1000)

root.mainloop()
```

**输出：**
![](img/5f253ac0ca003d1d6e360f59c8e1ff2c.png)