# 如何在 Seaborn 中用数据点制作小提琴图？

> 原文：[https://www.geeksforgeeks.org/how-to-make-violinplot-with-data-points-in-seaborn/](https://www.geeksforgeeks.org/how-to-make-violinplot-with-data-points-in-seaborn/)

[小提琴图](https://www.geeksforgeeks.org/violinplot-using-seaborn-in-python/)的活动类似于箱线图或须线图，因为它显示了一个或多个分类变量的定量数据分布。在多个单元格中展示数据是一种高效且吸引人的方式。“宽格式”数据框有助于维护可以在图表上绘制的每个数字列。可以使用 NumPy 或 Python 对象，但 Pandas 对象更好，因为相关名称将用于注释坐标轴。在这篇文章中，我们将看到如何用数据点制作小提琴图。

> **语法：** `seaborn.violinplot(x=None, y=None, hue=None, data=None, **kwargs)`
>
> **参数：**
> `x`, `y`, `hue`：用于绘制长格式数据的输入。
> `data`：用于绘图的数据集。
> `scale`：用来缩放每把小提琴宽度的方法。
>
> **返回：** 该方法返回绘制了图形的坐标轴对象。

**我们先创建一个简单的小提琴图：**

### 蟒蛇 3

```py
# Python program to illustrate
# violinplot using inbuilt data-set
# given in seaborn

# importing the required module
import seaborn

# use to set style of background of plot
seaborn.set(style = 'whitegrid')

# loading data-set
tip = seaborn.load_dataset('tips')

seaborn.violinplot(x='day', y='tip', data=tip)
```

**输出：**

![](img/d46211924779346227f761322b12c4d6.png)

**方法 1：** 采用带状图。

### 蟒蛇 3

```py
# Python program to illustrate
# violinplot using inbuilt data-set
# given in seaborn

# importing the required module
import seaborn

# use to set style of background of plot
seaborn.set(style = 'whitegrid')

# loading data-set
tip = seaborn.load_dataset('tips')

seaborn.violinplot(x ='day', y ='tip',
                   data = tip)

seaborn.stripplot(x = "day", y = "tip",
                  color = 'black',
                  data = tip)
```

**输出：**

![](img/6bdcdd55a6fa4630e4a160ee84c04aaa.png)

**方法二：** 利用蜂群图。

### 蟒蛇 3

```py
# Python program to illustrate
# violinplot using inbuilt data-set
# given in seaborn

# importing the required module
import seaborn

# use to set style of background of plot
seaborn.set(style = 'whitegrid')

# loading data-set
tip = seaborn.load_dataset('tips')

seaborn.violinplot(x ='day', y ='tip',
                data = tip)

seaborn.swarmplot(x ='day', y ='tip',
                  data = tip,
                  color = "white")
```

**输出：**

![](img/6bb1a55049deae89b180556c7c2741eb.png)

**方法三：** 使用 `inner` 参数。

### 蟒蛇 3

```py
# Python program to illustrate
# violinplot using inbuilt data-set
# given in seaborn

# importing the required module
import seaborn

# use to set style of background of plot
seaborn.set(style = 'whitegrid')

# loading data-set
tip = seaborn.load_dataset('tips')

seaborn.violinplot(x ='day', y ='tip',
                data = tip, inner = "points")
```

**输出：**

![](img/2bd3383e4316b0cd878b45c7220c52a7.png)