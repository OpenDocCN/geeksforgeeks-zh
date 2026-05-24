# Python | 使用 Plotly 进行地理绘图

> 原文：[https://www.geeksforgeeks.org/python-geographical-plotting-using-plotly/](https://www.geeksforgeeks.org/python-geographical-plotting-using-plotly/)

地理绘图用于展示世界地图以及一个国家下的州级数据。主要用于数据分析师检查农业出口或可视化此类数据。

`plotly` 是一个 Python 库，用来设计图形，尤其是交互式图形。它可以绘制各种图形和图表，如直方图、条形图、箱线图、展开图等。它主要用于数据分析以及财务分析。`plotly` 是一个交互式可视化库。

`cufflinks` 与 `pandas` 进行连接，可以直接创建数据框的图形和图表。`choropleth` 用来描述美国的地理绘图。`choropleth` 用于绘制世界地图和其他许多地图。

## 命令安装

```py
pip install plotly 
```

## 实现代码

```py
# Python program to plot 
# geographical data using plotly

# importing all necessary libraries
import plotly.plotly as py
import plotly.graph_objs as go
import pandas as pd

# some more libraries to plot graph
from plotly.offline import download_plotlyjs, init_notebook_mode, iplot, plot

# To establish connection
init_notebook_mode(connected = True)

# type defined is choropleth to
# plot geographical plots
data = dict(type = 'choropleth',

# location: Arizoana, California, Newyork
            locations = ['AZ', 'CA', 'NY'],

# States of USA
            locationmode = 'USA-states',

# colorscale can be added as per requirement
            colorscale = 'Portland',

# text can be given anything you like
            text = ['text 1', 'text 2', 'text 3'],
            z = [1.0, 2.0, 3.0],
            colorbar = {'title': 'Colorbar Title Goes Here'})

layout = dict(geo ={'scope': 'usa'})

# passing data dictionary as a list 
choromap = go.Figure(data = [data], layout = layout)

# plotting graph
iplot(choromap)
```

## 输出

![map](img/21822fc1dfb2a6d373129b165b4dd6d1.png)