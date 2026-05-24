# Python 中的 `plotly.express.scatter_3d()` 函数

> 原文: [https://www.geeksforgeeks.org/plotly-express-scatter_3d-function-in-python/](https://www.geeksforgeeks.org/plotly-express-scatter_3d-function-in-python/)

Python 的 Plotly 库对于数据可视化和简单容易地理解数据非常有用。Plotly graph 对象是易于使用的高级绘图界面。

## `plotly.express.scatter_3d()` 函数

该功能用于创建三维散点图，并可用于熊猫数据帧。在散点图中，数据帧的每一行都由三维空间中的符号标记表示。

> 语法: `plotly.express.scatter_3d(data_frame=None, x=None, y=None, z=None, color=None, symbol=None, size=None, text=None, hover_name=None, hover_data=None, custom_data=None, error_x=None, error_x_minus=None, error_y=None, error_y_minus=None, error_z=None, error_z_minus=None, animation_frame=None, animation_group=None, category_orders=None, labels=None, size_max=None, color_discrete_sequence=None, color_discrete_map=None, symbol_sequence=None, symbol_map=None, opacity=None, log_x=False, log_y=False, log_z=False, range_x=None, range_y=None, range_z=None, title=None, template=None, width=None, height=None)`

**参数:**

`data_frame`: 列名需要传递 DataFrame 或类似数组或 dict。

`x`, `y`, `z`: 这些参数要么是 `data_frame` 中某列的名称，要么是 pandas Series 或 array_like 对象。来自该列或 array_like 的值分别用于在笛卡尔坐标中沿 x、y 和 z 轴定位标记。

`color`: 该参数为标记指定颜色。

`symbol`: 此参数用于将符号分配给标记。它或者是 `data_frame` 中某列的名称，或者是 pandas Series 或 array_like 对象。

`size`: 该参数用于分配标记尺寸。它或者是 `data_frame` 中某列的名称，或者是 pandas Series 或 array_like 对象。

`hover_name`: 此列或类似数组的值以粗体显示在悬停工具提示中。

`hover_data`: 此参数用于在悬停工具提示或元组中以 bool 或格式字符串作为第一个元素出现，列表状数据作为第二个元素出现在悬停中这些列的值作为额外数据出现在悬停工具提示中。

## 例 1

```py
# Python program to demonstrate 3D scatter
# plot

import plotly.express as px

df = px.data.tips()

plot = px.scatter_3d(df, x = 'day', 
                     y = 'total_bill',
                     z='sex')
plot.show()
```

**输出:**

![](img/355e6e2eac9839faec7b657f06a3e79c.png)

## 示例 2: 使用颜色参数

```py
# Python program to demonstrate scatter
# plot

import plotly.express as px

df = px.data.tips()

plot = px.scatter_3d(df, x = 'day', 
                     y = 'total_bill',
                     z = 'sex', 
                     color = 'time')
plot.show()
```

**输出:**

![](img/2864390e6dd6b0425fd4d1555fb803ef.png)

## 例 3

```py
# Python program to demonstrate scatter
# plot

import plotly.express as px

df = px.data.tips()

plot = px.scatter_3d(df, x = 'day', 
                     y = 'total_bill', 
                     z = 'sex', 
                     color = 'time',
                     symbol = 'total_bill')
plot.show()
```

**输出:**

![](img/a4e409533e51c37e27f06684048e859e.png)