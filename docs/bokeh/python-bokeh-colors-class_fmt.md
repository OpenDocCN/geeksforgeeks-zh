# Python Bokeh–颜色类

> 原文：[https://www.geeksforgeeks.org/python-bokeh-colors-class/](https://www.geeksforgeeks.org/python-bokeh-colors-class/)

Bokeh 是一款 Python 交互数据可视化库。它使用 HTML 和 JavaScript 来渲染它的图。它以现代网络浏览器为呈现目标，提供优雅、简洁的新颖图形结构和高性能交互性。

在本文中，我们将了解 Bokeh 的 `Colors`。Bokeh 中有 5 种不同的颜色类别：

1.  `bokeh.colors.Color`
2.  `bokeh.colors.HSL`
3.  `bokeh.colors.RGB`
4.  `bokeh.colors.groups`
5.  `bokeh.colors.named`

## `bokeh.colors.Color`

这是代表颜色对象的基类。该类中的方法有：

*   `clamp()`
*   `copy()`
*   `darken()`
*   `from_hsl()`
*   `from_rgb()`
*   `lighten()`
*   `to_css()`
*   `to_hsl()`
*   `to_rgb()`

## `bokeh.colors.HSL`

这提供了一个用 HSL 格式表示颜色的类，即色相、饱和度和明度。

**示例：** 我们将绘制一个字形，并使用 HSL 格式对其进行着色。

### Python 3

```py
# importing the modules
from bokeh.plotting import figure, output_file, show
from bokeh.colors import HSL

# file to save the model
output_file("gfg.html")

# instantiating the figure object
graph = figure(title = "Bokeh Color")

# the point to be plotted
x = 0
y = 0

# HSL color
hue = 0
saturation = 0.47
lightness = 0.58
color = HSL(h = hue,
            s = saturation,
            l = lightness)

# plotting the graph
graph.dot(x, y, size = 1000,
          color = color.to_rgb())

# displaying the model
show(graph)
```

**输出：**

![](img/effcaad658f838f8470930fca6854267.png)

## `bokeh.colors.RGB`

该类通过指定红色、绿色和蓝色通道来表示颜色。

**示例：** 我们将绘制一个字形，并使用 RGB 格式将其染成浅绿色。

### Python 3

```py
# importing the modules
from bokeh.plotting import figure, output_file, show
from bokeh.colors import RGB

# file to save the model
output_file("gfg.html")

# instantiating the figure object
graph = figure(title = "Bokeh Color")

# the point to be plotted
x = 0
y = 0

# RGB color
red = 144
green = 238
blue = 144
color = RGB(r = red,
            g = green,
            b = blue)

# plotting the graph
graph.dot(x, y, size = 1000,
          color = color)

# displaying the model
show(graph)
```

**输出：**

![](img/a6f8470e091d834fdad7aa4a782e772a.png)

## `bokeh.colors.groups`

这表示根据一般色调将 CSS 命名的颜色分成有用的组。每种颜色都有自己的类别，有多种不同色调的变体。本课程中的颜色列表为：

1.  **黑色：** ` gainsboro`, `lightgray`, `silver`, `darkgray`, `dimgray`, `lightslategray`, `slategray`, `darkslategray`, `black`
2.  **蓝色：** `lightsteelblue`, `powderblue`, `lightskyblue`, `skyblue`, `lightslateblue`, `deepskyblue`, `dodgerblue`, `cornflowerblue`, `steelblue`, `royalblue`, `blue`, `mediumblue`, `darkblue`, `navy`, `midnightblue`
3.  **棕色：** `cornsilk`, `blanchedalmond`, `bisque`, `navajowhite`, `wheat`, `burlywood`, `tan`, `rosybrown`, `sandybrown`, `goldenrod`, `darkgoldenrod`, `peru`, `chocolate`, `saddlebrown`, `sienna`, `brown`, `maroon`
4.  **青色：** `mediumaquamarine`, `aquamarine`, `cyan`, `lightcyan`, `paleturquoise`, `aquamarine`, `turquoise`, `mediumturquoise`, `darkturquoise`, `lightseagreen`, `cadetblue`, `darkcyan`, `teal`
5.  **绿色：** `darkolivegreen`, `olive`, `olivedrab`, `yellowgreen`, `limegreen`, `lime`, `lawngreen`, `chartreuse`, `greenyellow`, `springgreen`, `mediumspringgreen`, `lightgreen`, `palegreen`, `darkseagreen`, `mediumseagreen`, `seagreen`, `forestgreen`, `green`, `darkgreen`
6.  **橙色：** `orange`, `tomato`, `coral`, `darkorange`, `orangered`
7.  **粉红色：** `pink`, `lightpink`, `hotpink`, `deeppink`, `palevioletred`, `mediumvioletred`
8.  **紫色：** `lavender`, `thistle`, `plum`, `violet`, `orchid`, `fuchsia`, `magenta`, `mediumorchid`, `mediumpurple`, `blueviolet`, `darkviolet`, `darkorchid`, `darkmagenta`, `indigo`, `darkslateblue`, `mediumslateblue`
9.  **红色：** `lightsalmon`, `salmon`, `darksalmon`, `lightcoral`, `indianred`, `crimson`, `firebrick`, `darkred`, `red`
10. **白色：** `white`, `snow`, `honeydew`, `mintcream`, `azure`, `aliceblue`, `ghostwhite`, `whitesmoke`, `seashell`, `beige`, `oldlace`, `floralwhite`, `ivory`, `antiquewhite`, `linen`, `lavenderblush`, `mistyrose`
11. **黄色：** `yellow`, `lightyellow`, `lemonchiffon`, `lightgoldenrodyellow`, `papayawhip`, `moccasin`, `peachpuff`, `palegoldenrod`, `khaki`, `darkkhaki`, `gold`

**示例：** 我们将绘制多个字形，并使用颜色组对它们进行着色。

### Python 3

```py
# importing the modules
from bokeh.plotting import figure, output_file, show
from bokeh.colors.groups import purple, yellow, blue

# file to save the model
output_file("gfg.html")

# instantiating the figure object
graph = figure(title = "Bokeh Color")

# the point to be plotted
x = [-2, 0, 2]
y = 0

# color groups
color = [purple()._colors[purple()._colors.index("Fuchsia")],
         yellow()._colors[yellow()._colors.index("Khaki")],
         blue()._colors[blue()._colors.index("RoyalBlue")]]

# plotting the graph
graph.dot(x, y, size = 1000,
          color = color)

# displaying the model
show(graph)
```