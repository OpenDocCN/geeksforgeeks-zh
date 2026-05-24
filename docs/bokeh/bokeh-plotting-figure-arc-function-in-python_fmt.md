# Python中的`bokeh.plotting.figure.arc()`函数

> 原文：[https://www.geeksforgeeks.org/bokeh-plotting-figure-arc-function-in-python/](https://www.geeksforgeeks.org/bokeh-plotting-figure-arc-function-in-python/)

[Bokeh](https://www.geeksforgeeks.org/python-data-visualization-using-bokeh/#:~:text=Python%20%7C%20Data%20visualization%20using%20Bokeh%20in%20Django%20and%20flask%20apps.)是Python中的数据可视化库，提供高性能的交互式图表和图，输出可以通过笔记本、html、服务器等多种媒介获得。`Figure`类创建一个新的图形用于绘图。它是绘图的一个子类，通过默认轴、网格、工具等简化绘图创建。

## `bokeh.plotting.figure.arc()`函数

bokeh库绘图模块中的`arc()`函数用于配置弧字形并添加到本图中。

> **语法：** `arc(x, y, radius, start_angle, end_angle, direction='anticlock', *, end_angle_units='rad', line_alpha=1.0, line_cap='butt', line_color='black', line_dash=[], line_dash_offset=0, line_join='miter', line_width=1, name=None, radius_units='data', start_angle_units='rad', tags=[], **kwargs)`
>
> **参数：** 该方法接受以下描述的参数：
>
> *   `x`：该参数是弧中心的x坐标。
> *   `y`：该参数是弧中心的y坐标。
> *   `start_angle`：此参数是开始弧的角度。
> *   `end_angle`：此参数是结束弧的角度。
> *   `direction`：该参数是在起始角和结束角之间进行描边的方向。
> *   `fill_alpha`：该参数是弧的填充alpha值。
> *   `fill_color`：该参数是弧的填充颜色值。
> *   `line_alpha`：该参数为步骤的line alpha值，默认值为1.0。
> *   `line_cap`：此参数是默认值为butt的步骤的线帽值。
> *   `line_color`：此参数是默认值为黑色的步骤的线条颜色值。
> *   `line_dash`：此参数是步骤的线划值，默认值为[]。
> *   `line_dash_offset`：此参数是默认值为0的步骤的线划偏移量。
> *   `line_join`：该参数是斜面默认值的步骤的线连接值。
> *   `line_width`：该参数为步长的线宽值，默认值为1。
> *   `mode`：该参数可以是三个值中的一个：["before", "after", "center"]。
> *   `name`：此参数是用户为此型号提供的名称。
> *   `tags`：此参数是用户为此模型提供的值。
>
> **其他参数：** 这些参数是`**kwargs`，描述如下：
>
> *   `alpha`：此参数用于一次性设置所有alpha关键字参数。
> *   `color`：此参数用于一次性设置所有颜色关键字参数。
> *   `legend_field`：此参数是数据源中应该用于分组的列的名称。
> *   `legend_group`：此参数是数据源中应该用于分组的列的名称。
> *   `legend_label`：此参数是图例条目，与此处提供的文本完全一致。
> *   `muted`：该参数包含bool值。
> *   `name`：此参数是可选的用户提供的名称，用于附加到渲染器。
> *   `source`：此参数为用户提供的数据源。
> *   `view`：该参数是过滤数据源的视图。
> *   `visible`：该参数包含布尔值。
> *   `x_range_name`：此参数是用于映射x坐标的额外范围的名称。
> *   `y_range_name`：此参数是用于映射y坐标的额外范围的名称。
> *   `level`：此参数指定此字形的渲染等级顺序。
>
> **返回：** 该方法返回`GlyphRenderer`值。

以下示例说明了`bokeh.plotting.figure.arc()`函数在`bokeh.plotting`中的用法：

**示例1：**

```py
# Implementation of bokeh function

import numpy as np
from bokeh.plotting import figure, output_file, show

plot = figure(plot_width = 300, plot_height = 300)
plot.arc(x =[1, 2, 3], y =[3, 2, 1], radius = 0.3,
         start_angle = 0.4, end_angle = 4.8,
         color ="green", alpha = 0.6)

show(plot)
```

**输出：**
![](img/00d90b232020ca24e6bf4b007f685a0e.png)

**示例2：**

```py
# Implementation of bokeh function

import numpy as np
from bokeh.plotting import figure, output_file, show

N = 9
x = np.linspace(-2, 2, N)
y = x**2
r = x / 15.0 + 0.3

plot = figure(plot_width = 300, plot_height = 300)
plot.arc(x = x, y = y, radius = r,
         start_angle = 0.6, end_angle = 4.8,
         color ="green", alpha = 0.6, line_width = 3)

show(plot)
```

**输出：**
![](img/ceb6c148f0c1a18120fc88936077a607.png)