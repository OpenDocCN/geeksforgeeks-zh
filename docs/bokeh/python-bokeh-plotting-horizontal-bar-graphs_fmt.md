# Python Bokeh–绘制水平条形图

> 原文: [https://www.geeksforgeeks.org/python-bokeh-plotting-horizontal-bar-graphs/](https://www.geeksforgeeks.org/python-bokeh-plotting-horizontal-bar-graphs/)

Bokeh 是一个 Python 交互式数据可视化工具。它使用 HTML 和 JavaScript 来渲染它的图。它以现代网络浏览器为呈现目标，提供优雅、简洁的新颖图形结构和高性能交互性。

Bokeh 可用于绘制水平条形图。可以使用`plotting`模块的`hbar()`方法绘制横条图。

## `plotting.figure.hbar()`

> **语法:** `hbar(参数)`
>
> **参数:**
>
> *   `y` : 横条中心的 y 坐标
> *   `height`: 水平杆的厚度
> *   `right`: 右边缘的 x 坐标
> *   `left`: 左边缘的 x 坐标，默认为 0
> *   `fill_alpha`: 填充水平条的α值
> *   `fill_color`: 水平条的填充颜色值
> *   `line_alpha`: 水平条的阴影阿尔法值，默认为 1
> *   `line_color`: 横条的阴影颜色值，默认为黑色
> *   `line_dash`: 水平条的阴影额外值
> *   `line_dash_offset`: 横条的阴影图案值
> *   `line_width`: 横条的阴影比例值，默认为 12
> *   `line_cap`: 横条的阴影重量值，默认为 1
> *   `line_join`: line alpha 的百分比值，默认为 1
> *   `line_color`: 线的线帽值，默认为对接
> *   `line_dash`: 线条的颜色，默认为黑色
> *   `line_dash`: value of line dash such as :
>     *   `solid`
>     *   `dashed`
>     *   `dotted`
>     *   `dotdash`
>     *   `dashdot`
>
>     默认为实心
>
> *   `line_dash_offset`: 线划偏移量的值，默认为 0
> *   `line_join`: 线连接的值，默认为斜角
> *   `line_width`: 线宽值，默认为 1
> *   `name`: 用户提供的型号名称
> *   `tags`: 用户为模型提供的值
>
> **其他参数:**
>
> *   `alpha` : 一次性设置所有 alpha 关键字参数
> *   `color`: 一次性设置所有颜色关键字参数
> *   `legend_field`: 数据源中应使用的列的名称
> *   `legend_group`: 数据源中应使用的列的名称
> *   `legend_label`: 标记图例条目
> *   `muted`: 确定字形是否应该渲染为静音，默认为假
> *   `name`: 附加到渲染器的可选用户提供的名称
> *   `source`: 用户提供的数据源
> *   `view`: 用于过滤数据源的视图
> *   `visible`: 决定是否渲染字形，默认为真
> *   `x_range_name`: 用于映射 x 坐标的额外范围的名称
> *   `y_range_name`: 用于映射 y 坐标的额外范围的名称
> *   `level`: 指定此字形的渲染等级顺序
>
> **返回:** 类的一个对象`GlyphRenderer`

## 示例 1

在本例中，我们将使用默认值绘制图表。

```py
# importing the modules
from bokeh.plotting import figure, output_file, show

# file to save the model
output_file("gfg.html")

# instantiating the figure object
graph = figure(title = "Bokeh Horizontal Bar Graph")

# y-coordinates to be plotted
y = [1, 2, 3, 4, 5]

# x-coordinates of the right edges
right = [1, 2, 3, 4, 5]

# height / thickness of the bars
height = 0.5

# plotting the graph
graph.hbar(y,
           right = right,
           height = height)

# displaying the model
show(graph)
```

**输出:**
![](img/71548a7da47c3c90b61a210d717a9127.png)

## 示例 2

在本例中，我们将绘制具有不同参数的水平条。

```py
# importing the modules
from bokeh.plotting import figure, output_file, show

# file to save the model
output_file("gfg.html")

# instantiating the figure object
graph = figure(title = "Bokeh Horizontal Bar Graph")

# name of the x-axis
graph.xaxis.axis_label = "x-axis"

# name of the y-axis
graph.yaxis.axis_label = "y-axis"

# y-coordinates to be plotted
y = [1, 2, 3, 4, 5]

# x-coordinates of the right edges
right = [1, 2, 3, 4, 5]

# height / thickness of the bars
height = [0.5, 0.4, 0.3, 0.2, 0.1]

# color values of the bars
fill_color = ["yellow", "pink", "blue", "green", "purple"]

# plotting the graph
graph.hbar(y,
           right = right,
           height = height,
           fill_color = fill_color)

# displaying the model
show(graph)
```

**输出:**
![](img/91e7ecf68bbe43bcc7f438f7f626c492.png)