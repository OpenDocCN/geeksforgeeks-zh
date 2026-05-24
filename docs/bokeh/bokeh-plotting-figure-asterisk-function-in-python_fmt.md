# Python 中的 Bokeh plotting.figure.asterisk() 函数

> 原文: [https://www.geeksforgeeks.org/bokeh-plotting-figure-asterisk-function-in-python/](https://www.geeksforgeeks.org/bokeh-plotting-figure-asterisk-function-in-python/)

[Bokeh](https://www.geeksforgeeks.org/python-data-visualization-using-bokeh/#:~:text=Python%20%7C%20Data%20visualization%20using%20Bokeh, in%20Django%20and%20flask%20apps.) 是 Python 中的数据可视化库，提供高性能的交互式图表和图，输出可以通过笔记本、html、服务器等多种媒介获得。`图形类`创建一个新的图形用于绘图。它是绘图的一个子类，通过默认轴、网格、工具等简化绘图创建。

## Bokeh plotting.figure.asterisk() 函数

Bokeh 库绘图模块中的 `asterisk()` 函数用于配置星号字形并添加到本图中。

> **语法:** `asterisk(x, y, size=4, angle=0.0, angle_units='rad', fill_alpha=1.0, fill_color='gray', line_alpha=1.0, line_cap='butt', line_color='black', line_dash=[], line_dash_offset=0, line_join='miter', line_width=1, name=None, tags=[], **kwargs)`
>
> **参数:** 该方法接受以下描述的参数:
>
> *   `x`: 该参数是标记中心的 x 坐标。
> *   `y`: 此参数是标记中心的 y 坐标。
> *   `size`: 该参数是以屏幕空间单位表示的标记尺寸(直径)值。
> *   `angle`: 此参数是旋转标记的角度。
> *   `fill_alpha`: 该参数是标记的填充 alpha 值。
> *   `fill_color`: 该参数是标记的填充颜色值。
> *   `line_alpha`: 此参数是默认值为 1.0 的标记的 line alpha 值。
> *   `line_cap`: 此参数是默认值为 butt 的标记的线帽值。
> *   `line_color`: 此参数是标记的线条颜色值，默认值为黑色。
> *   `line_dash`: 此参数是标记的划线值，默认值为[]。
> *   `line_dash_offset`: 此参数是标记的线划偏移量值，默认值为 0。
> *   `line_join`: 该参数是 miter 默认值标记的线连接值。
> *   `line_width`: 该参数是默认值为 1 的标记的线宽值。
> *   `mode`: 该参数可以是三个值中的一个: ["before", "after", "center"]。
> *   `name`: 此参数是用户为此型号提供的名称。
> *   `tags`: 此参数是用户为此模型提供的值。
>
> **其他参数:** 这些参数是 `**kwargs`，描述如下:
>
> *   `alpha`: 此参数用于一次性设置所有 alpha 关键字参数。
> *   `color`: 此参数用于一次性设置所有颜色关键字参数。
> *   `legend_field`: 此参数是数据源中应该用于分组的列的名称。
> *   `legend_group`: 此参数是数据源中应该用于分组的列的名称。
> *   `legend_label`: 此参数是图例条目，与此处提供的文本完全一致。
> *   `muted`: 该参数包含 bool 值。
> *   `name`: 此参数是可选的用户提供的名称，用于附加到渲染器。
> *   `source`: 此参数为用户提供的数据源。
> *   `view`: 该参数是过滤数据源的视图。
> *   `visible`: 该参数包含布尔值。
> *   `x_range_name`: 此参数是用于映射 x 坐标的额外范围的名称。
> *   `y_range_name`: 此参数是用于映射 y 坐标的额外范围的名称。
> *   `level`: 此参数指定此字形的渲染等级顺序。
>
> **返回:** 该方法返回 `GlyphRenderer` 值。

以下示例说明了 `bokeh.plotting` 中的 `bokeh.plotting.figure.asterisk()` 函数:

**示例 1:**

```py
# Implementation of bokeh function

import numpy as np
from bokeh.plotting import figure, output_file, show

plot = figure(plot_width = 300, plot_height = 300)
plot.asterisk(x =[1, 2, 3], y =[3, 2, 1], size = 30,
         color ="green", alpha = 0.6)

show(plot)
```

**输出:**
![](img/7e3458cff72c5f94ef5210b4b81b54ea.png)

**例 2:**

```py
# Implementation of bokeh function

import numpy as np
from bokeh.plotting import figure, output_file, show

N = 9
x = np.linspace(-2, 2, N)
y = x**2
sizes = np.linspace(20, 50, N)

plot = figure(plot_width = 300, plot_height = 300)
plot.asterisk(x = x, y = y, size = sizes,
         color ="green", alpha = 0.6, line_width = 3)

show(plot)
```

**输出:**
![](img/75fa4d37c22983ffc827919756217205.png)