# Python中的plotly.express.scatter_polar()函数

> 原文：[https://www.geeksforgeeks.org/plotly-express-scatter_polar-function-in-python/](https://www.geeksforgeeks.org/plotly-express-scatter_polar-function-in-python/)

Python的Plotly库对于数据可视化和简单容易地理解数据非常有用。Plotly graph对象是易于使用的高级绘图界面。

## plotly.express.scatter_polar()函数

该功能用于创建极坐标图。极坐标图表示沿径向和角度轴的数据。

> 语法：`plotly.express.scatter_polar(data_frame=None, r=None, theta=None, color=None, symbol=None, size=None, hover_name=None, hover_data=None, title=None, template=None, width=None, height=None)`
>
> 参数：
>
> `data_frame`：列名需要传递DataFrame或类似数组或dict。
>
> `r`, `theta`：该参数或者是`data_frame`中某列的名称，或者是pandas Series或array_like对象。用于在极坐标中分别沿径向轴和角向轴定位标记。
>
> `color`：该参数为标记指定颜色。
>
> `symbol`：此参数用于将符号分配给标记。它或者是`data_frame`中某列的名称，或者是pandas Series或array_like对象。
>
> `size`：该参数用于分配标记尺寸。它或者是`data_frame`中某列的名称，或者是pandas Series或array_like对象。
>
> `hover_name`：此列或类似数组的值以粗体显示在悬停工具提示中。
>
> `hover_data`：此参数用于在悬停工具提示或元组中以bool或格式字符串作为第一个元素出现，列表状数据作为第二个元素出现在悬停中这些列的值作为额外数据出现在悬停工具提示中。
>
> `title`：图标题。
>
> `width`：以像素为单位的图形宽度。
>
> `height`：以像素为单位的图形高度。

### 例1：

```py
import plotly.express as px

df = px.data.tips()

plot = px.scatter_polar(df, r = 'day', 
                        theta = 'total_bill')
plot.show()
```

**输出：**

![](img/d65ec4b51c4eaad1c626c84dd643cb76.png)

### 示例2：使用颜色参数

```py
import plotly.express as px

df = px.data.tips()

plot = px.scatter_polar(df, r = 'day',
                        theta = 'total_bill', 
                        color='time')
plot.show()
```

**输出：**

![](img/5426f5e899b1392e2791c08e46af3421.png)

### 示例3：使用符号参数

```py
import plotly.express as px

df = px.data.tips()

plot = px.scatter_polar(df, r = 'day', 
                        theta = 'total_bill',
                        color = 'time',
                        symbol = 'tip')
plot.show()
```

**输出：**

![](img/6095eb9e8f12172b95505ab59ba9b4b4.png)