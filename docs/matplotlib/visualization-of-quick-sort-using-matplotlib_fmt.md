# 使用 Matplotlib 可视化快速排序

> 原文：[https://www.geeksforgeeks.org/visualization-of-quick-sort-using-matplotlib/](https://www.geeksforgeeks.org/visualization-of-quick-sort-using-matplotlib/)

通过分析和比较为比较和交换元素而进行的操作数量，可视化算法使理解它们变得更加容易。为此，我们将使用 `matplotlib` 绘制条形图来表示数组的元素。

## 进场:

1.  我们将生成一个随机元素数组。
2.  算法将被应用于该数组，并且为了可视化目的，将使用 `yield` 语句代替 `return` 语句。
3.  我们将在比较和交换后生成数组的当前状态。因此，算法将返回一个生成器对象。
4.  `Matplotlib` 动画将用于可视化数组的比较和交换。
5.  数组将被存储在 `matplotlib` 条形容器对象（`bar_rects`）中，其中每个条形的高度将等于数组中对应元素的值。
6.  `Matplotlib` 动画的内置 `FuncAnimation` 方法将容器和生成器对象传递给用于创建动画的函数。动画的每一帧对应生成器的一次迭代。
7.  重复的动画函数将把矩形的高度设置为元素的值。

## 蟒 3

```py
# import all the modules
import matplotlib.pyplot as plt
from matplotlib.animation import FuncAnimation
from mpl_toolkits.mplot3d import axes3d
import matplotlib as mp
import numpy as np
import random

# quicksort function
def quicksort(a, l, r):
    if l >= r:
        return
    x = a[l]
    j = l
    for i in range(l + 1, r + 1):
        if a[i] <= x:
            j += 1
            a[j], a[i] = a[i], a[j]
        yield a
    a[l], a[j]= a[j], a[l]
    yield a

# yield from statement used to yield
    # the array after dividing
    yield from quicksort(a, l, j-1)
    yield from quicksort(a, j + 1, r)

# function to plot bars
def showGraph():

# for random unique values
    n = int(input("enter array size\n"))
    a = [i for i in range(1, n + 1)]
    random.shuffle(a)
    datasetName ='Random'

# generator object returned by the function
    generator = quicksort(a, 0, n-1)
    algoName = 'Quick Sort'

# style of the chart
    plt.style.use('fivethirtyeight')

# set colors of the bars
    data_normalizer = mp.colors.Normalize()
    color_map = mp.colors.LinearSegmentedColormap(
        "my_map",
        {
            "red": [(0, 1.0, 1.0),
                    (1.0, .5, .5)],
            "green": [(0, 0.5, 0.5),
                      (1.0, 0, 0)],
            "blue": [(0, 0.50, 0.5),
                     (1.0, 0, 0)]
        }
    )

fig, ax = plt.subplots()

# bar container
    bar_rects = ax.bar(range(len(a)), a, align ="edge",
                       color = color_map(data_normalizer(range(n))))

# setting the limits of x and y axes
    ax.set_xlim(0, len(a))
    ax.set_ylim(0, int(1.1 * len(a)))
    ax.set_title("ALGORITHM : "+ algoName + "\n" + "DATA SET : " +
             datasetName, fontdict = {'fontsize': 13, 'fontweight':
                                      'medium', 'color' : '#E4365D'})

# the text to be shown on the upper left indicating the number of iterations
    # transform indicates the position with relevance to the axes coordinates.
    text = ax.text(0.01, 0.95, "", transform = ax.transAxes, color = "#E4365D")
    iteration = [0]

def animate(A, rects, iteration):
        for rect, val in zip(rects, A):

# setting the size of each bar equal to the value of the elements
            rect.set_height(val)
        iteration[0] += 1
        text.set_text("iterations : {}".format(iteration[0]))

# call animate function repeatedly
    anim = FuncAnimation(fig, func = animate,
        fargs = (bar_rects, iteration), frames = generator, interval = 50,
        repeat = False)
    plt.show()

showGraph()
```