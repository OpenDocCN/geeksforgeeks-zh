# Python中的`bokeh.plotting.figure.cross()`函数

> 原文：[https://www.geeksforgeeks.org/bokeh-plotting-figure-cross-function-in-python/](https://www.geeksforgeeks.org/bokeh-plotting-figure-cross-function-in-python/)

`Bokeh`是Python中的数据可视化库，提供高性能的交互式图表和绘图，输出可以通过笔记本、HTML、服务器等多种媒介获得。`figure`类新建一个用于绘图的图形。它是绘图的一个子类，通过默认轴、网格、工具等简化绘图创建。

## `bokeh.plotting.figure.cross()`函数

`bokeh`库绘图模块中的`cross()`函数用于配置十字字形并添加到本图中。

> **语法：** `cross(x, y, size=4, angle=0.0, angle_units='rad', fill_alpha=1.0, fill_color='gray', line_alpha=1.0, line_cap='butt', line_color='black', line_dash=[], line_dash_offset=0, line_join='miter', line_width=1, name=None, tags=[], **kwargs)`
>
> **参数：** 该方法接受以下描述的参数：
> *   `x`：该参数是标记中心的x坐标。
> *   `y`：此参数是标记中心的y坐标。
> *   `size`：该参数是以屏幕空间单位表示的标记尺寸（直径）值。
> *   `angle`：此参数是旋转标记的角度。
> *   `fill_color`：该参数是标记的填充颜色值。
> *   `line_color`：此参数是标记的线条颜色值，默认值为黑色。
> *   `line_dash`：此参数是标记的划线值，默认值为[]。
> *   `name`：此参数是用户为此型号提供的名称。
> *   `tags`：此参数是用户为此模型提供的值。
>
> **返回：** 该方法返回`GlyphRenderer`值。

以下示例说明了`bokeh.plotting.figure.cross()`函数在`bokeh.plotting`中的用法：

### 示例1

```python
# Implementation of bokeh function

import numpy as np
from bokeh.plotting import figure, output_file, show

plot = figure(plot_width=300, plot_height=300)
plot.cross(x=[1, 2, 3], y=[3, 7, 5],
           size=20, color="green", alpha=0.9)

show(plot)
```

**输出：**

![](img/56cba5da264851b632f17b804319f626.png)

### 示例2

```python
# Implementation of bokeh function

import numpy as np
from bokeh.plotting import figure, output_file, show

x = [1, 2, 3, 4, 5]
y = [6, 7, 8, 7, 3]

output_file("geeksforgeeks.html")

p = figure(plot_width=300, plot_height=300)

# add both a line and circles on the
# same plot
p.line(x, y, line_width=2)
p.cross(x, y, fill_color="red",
        line_color="green", size=25)

show(p)
```

**输出：**

![](img/a792ead01d28b210fdff5ea687f35783.png)