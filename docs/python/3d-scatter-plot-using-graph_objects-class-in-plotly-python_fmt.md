# 在 Plotly-Python 中使用 graph_objects 类的三维散点图

> 原文: [https://www.geeksforgeeks.org/3d-scatter-plot-using-graph_objects-class-in-plotly-python/](https://www.geeksforgeeks.org/3d-scatter-plot-using-graph_objects-class-in-plotly-python/)

**Plotly** 是一个 Python 库，用来设计图形，尤其是交互图形。它可以绘制各种图形和图表，如直方图、条形图、箱线图、展开图等。它主要用于数据分析以及财务分析。`plotly` 是一个交互式可视化库。

## 使用图形对象类的散点图

如果一个情节性的表达不能提供一个很好的起点，那么可以使用 `plotly.graph_objects` 中的 `Scatter3d` 类。散点图是那些图表，其中数据点以水平和垂直轴表示，以显示一个变量如何影响另一个变量。属性的模式决定数据点的外观。

> **语法:** `plotly.graph_objects.Scatter3d(arg=None, connectgaps=None, customdata=None, customdatasrc=None, error_x=None, error_y=None, error_z=None, hoverinfo=None, hoverinfosrc=None, hoverlabel=None, hovertemplatesrc=None, hovertext=None, hovertextsrc=None, ids=None, idssrc=None, legendgroup=None, line=None, marker=None, meta=None, metasrc=None, mode=None, name=None, opacity=None)`
>
> **参数:**
>
> `x` – 设置 x 坐标。
>
> `y` – 设置 y 坐标。
>
> `z` – 设置 z 坐标。
>
> `mode` – 确定该散射轨迹的绘制模式。

**例 1:**

```py
import plotly.express as px
import plotly.graph_objects as go

df = px.data.tips()

fig = go.Figure(data=[go.Scatter3d(x=df['total_bill'],
                                   y=df['time'],
                                   z=df['tip'],
                                   mode='markers')])
fig.show()
```

**输出:**

![](img/4d3d7bf6d92e83dadff78385fe829703.png)

**例 2:**

```py
import plotly.express as px
import plotly.graph_objects as go

df = px.data.iris()

fig = go.Figure(data=[go.Scatter3d(x=df['sepal_width'],
                                   y=df['sepal_length'],
                                   z=df['petal_length'],
                                   mode='markers')])
fig.show()
```

**输出:**

![](img/dd18d04fd60bd784ec11141cf63f85ea.png)

## 使用颜色缩放和标记样式呈现三维散点图

通俗地说，颜色缩放和标记样式是更有效地表示数据的一种方式，它使数据更容易理解。

**例 1:**

```py
import plotly.express as px
import plotly.graph_objects as go

df = px.data.iris()

fig = go.Figure(data=[go.Scatter3d(x=df['sepal_width'],
                                   y=df['sepal_length'],
                                   z=df['petal_length'],
                                   mode='markers',
                                   marker=dict(
                                       size=12,
                                       color=df['petal_width'],
                                       colorscale='Viridis',
                                       opacity=0.8
                                   )
)])

fig.show()
```

**输出:**

![](img/d9e0d567b61d331697cb755270a7011a.png)

**例 2:**

```py
import plotly.express as px
import plotly.graph_objects as go

df = px.data.tips()

fig = go.Figure(data=[go.Scatter3d(x=df['total_bill'],
                                   y=df['time'],
                                   z=df['day'],
                                   mode='markers',
                                   marker=dict(
                                       color=df['tip'],
                                       colorscale='Viridis',
                                       opacity=0.5
                                   )
)])
fig.show()
```

**输出:**

![](img/fca11f5c797d4d5f9c6b601c9c4b04bb.png)