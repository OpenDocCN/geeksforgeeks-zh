# Python 中 plotly.express.line_ternary() 函数

> 原文: [https://www.geeksforgeeks.org/plotly-express-line_ternary-function-in-python/](https://www.geeksforgeeks.org/plotly-express-line_ternary-function-in-python/)

Python 的 Plotly 库对于数据可视化和简单容易地理解数据非常有用。Plotly graph 对象是易于使用的高级绘图界面。

## plotly.express.line_ternary()

该方法用于创建三元线图。三元线图用于描绘等边三角形上三个变量的比值。

> 语法: `plotly.express.line_ternary(data_frame=None, a=None, b=None, c=None, color=None, line_dash=None, line_group=None, hover_name=None, hover_data=None, title=None, template=None, width=None, height=None)`
>
> 参数:
>
> `data_frame`: 列名需要传递 DataFrame 或类似数组或 dict。
>
> `a`, `b`, `c`: 这些参数要么是 `data_frame` 中某列的名称，要么是 pandas Series 或 array_like 对象。这些分别用于在三元坐标中沿 a、b 和 c 轴定位标记。
>
> `color`: 该参数为标记指定颜色。
>
> `hover_name`: 此列或类似数组的值以粗体显示在悬停工具提示中。
>
> `hover_data`: 此参数用于在悬停工具提示或元组中以 bool 或格式字符串作为第一个元素出现，列表状数据作为第二个元素出现在悬停中这些列的值作为额外数据出现在悬停工具提示中。
>
> `title`: 图的标题。
>
> `width`: 设置图形的宽度。
>
> `height`: 设置人物的高度。

## 示例 1

```python
import plotly.express as px

df = px.data.iris()

plot = px.line_ternary(df, a = 'sepal_width',
                       b = 'sepal_length',
                       c = 'petal_width')
plot.show()
```

**输出:**

![](img/5aa7e6e611838c08c0c849311202db31.png)

## 示例 2: 使用颜色和线组参数

```python
import plotly.express as px

df = px.data.iris()

plot = px.line_ternary(df, a = 'sepal_width',
                       b = 'sepal_length',
                       c = 'petal_width',
                       color = 'species',
                       line_group = 'species')
plot.show()
```

**输出:**

![](img/90cdec86e04d629bacaa53952b74e021.png)