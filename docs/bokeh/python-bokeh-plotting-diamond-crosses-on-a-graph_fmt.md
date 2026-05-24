# Python Bokeh–在图形上绘制菱形十字

> 原文: `https://www.geeksforgeeks.org/python-bokeh-plotting-diamond-crosses-on-a-graph/`

Bokeh 是一个 Python 交互式数据可视化工具。它使用 HTML 和 JavaScript 来渲染它的图。它以现代网络浏览器为呈现目标，提供优雅、简洁的新颖图形结构和高性能交互性。

Bokeh 可用于在图形上绘制带有十字的菱形。可以使用`plotting`模块的`diamond_cross()`方法在图形上绘制带有十字的菱形。

## `plotting.figure.diamond_cross()`

> **语法:** `diamond_cross(参数)`
>
> **参数:**
>
> *   `x` : 菱形十字标记中心的 x 坐标
> *   `y` : 菱形十字标记中心的 y 坐标
> *   `size`: 菱形十字标记的直径，默认为 4
> *   `angle`: 菱形十字标记的旋转角度，默认为 0
> *   `angle_units`: 角度的单位，默认为弧度
> *   `fill_alpha`: 菱形十字标记的填充α值
> *   `fill_color`: 菱形十字标记的填充颜色值
> *   `line_alpha`: line alpha 的百分比值，默认为 1
> *   `line_cap`: 线的线帽值，默认为对接
> *   `line_color`: 线条的颜色，默认为黑色
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
> *   `alpha`: 一次性设置所有 alpha 关键字参数
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

**示例 1:** 在本例中，我们将使用默认值绘制图表。我们已经提供了尺寸和填充颜色属性来使字形可见。

```py
# importing the modules
from bokeh.plotting import figure, output_file, show

# file to save the model
output_file("gfg.html")

# instantiating the figure object
graph = figure(title = "Bokeh Diamond Cross Graph")

# the points to be plotted
x = [-5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5]
y = [i ** 2 for i in x]

# plotting the graph
graph.diamond_cross(x, y, size = 25, fill_color = None)

# displaying the model
show(graph)
```

**输出:**
![](img/e7299ef661d4d74e54fcc6453390dcf8.png)

**示例 2:** 在本例中，我们将在其他参数旁边用虚线绘制菱形十字，菱形十字的大小与其值成比例。

```py
# importing the modules
from bokeh.plotting import figure, output_file, show

# file to save the model
output_file("gfg.html")

# instantiating the figure object
graph = figure(title = "Bokeh Diamond Cross Graph")

# name of the x-axis
graph.xaxis.axis_label = "x-axis"

# name of the y-axis
graph.yaxis.axis_label = "y-axis"

# the points to be plotted
x = [-5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5]
y = [i ** 2 for i in x]

# size of the diamonds
size = [i * 2 for i in y]

# angle of the diamonds
angle = 10

# fill color value
fill_color = None

# color of the line
line_color = "red"

# type of line
line_dash = "dotted"

# offset of line dash
line_dash_offset = 1

# width of the dashes
line_width = 10

# name of the legend
legend_label = "Sample Dashes"

# plotting the graph
graph.diamond_cross(x, y,
                    size = size,
                    angle = angle,
                    fill_color = fill_color,
                    line_color = line_color,
                    line_dash = line_dash,
                    line_dash_offset = line_dash_offset,
                    line_width = line_width,
                    legend_label = legend_label)

# displaying the model
show(graph)
```

**输出:**
![](img/699d984f1ccbd02796e7fee09e9176e8.png)