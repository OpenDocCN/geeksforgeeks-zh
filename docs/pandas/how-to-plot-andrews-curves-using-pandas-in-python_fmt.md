# 如何用 Python 中的 Pandas 绘制安德鲁斯曲线？

> 原文: [https://www.geeksforgeeks.org/how-to-plot-andrews-curves-using-pandas-in-python/](https://www.geeksforgeeks.org/how-to-plot-andrews-curves-using-pandas-in-python/)

安德鲁斯曲线通过将每个观察值映射到一个函数来可视化高维数据。它保留了平均值、距离和方差。它由公式给出:

> `t(n)= x_1/sqrt(2)+x_2 sin(n)+x_3 cos(n)+x_4 sin(2n)+x_5 cos(2n)+…`

可以使用绘图模块的 `andrews_curves()` 方法在图形上绘制安德鲁斯曲线。该函数生成安德鲁斯曲线的 `matplotlib` 图，用于可视化多变量数据的聚类。

## 语法

`andrews_curves(frame, class_column, ax=None, samples=200, color=None, colormap=None, **kwargs)`

## 参数

*   `frame`: 是要绘制的数据。
*   `class_column`: 这是包含类名的列的名称。
*   `ax`: 该参数是 `matplotlib axes` 对象。其默认值为 `None`。
*   `samples`: 此参数是每条曲线中要绘制的点数。
*   `color`: 这个参数是一个可选参数，它是用于不同类别的颜色列表或元组。
*   `colormap`: 此参数为 `string`/`matplotlib colormap` 对象。其默认值为 `None`。

## 返回

这个函数返回一个类的对象 `matplotlib.axis`。

## 示例 1

在以下示例中，数据框由 CSV 文件制成，该数据框用于绘制 `andrews_curves`。使用的 CSV 文件是[这里是](https://drive.google.com/file/d/1SbeM42PKEv0lsaypGISWOfdT46SzaLSO/view?usp=sharing)。

```py
# importing various package
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# making data frame from csv file
df = pd.read_csv(
    'C:\\Users\\digital india\\Desktop\\pand.csv'
)

# Creating Andrews curves
x = pd.plotting.andrews_curves(df, 'animal')

# ploting the Curve
x.plot()

# Display
plt.show()
```

**输出:**

![](img/7fb72e5e1f89a8553a226c52f4141561.png)

## 示例 2

```py
# importing various package
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# making data frame from csv file
df = pd.read_csv(
    'https://raw.github.com/pandas-dev/'
    'pandas/master/pandas/tests/io/data/csv/iris.csv'
)

# Creating Andrews curves
x = pd.plotting.andrews_curves(df, 'Name')

# ploting the Curve
x.plot()

# Display
plt.show()
```

**输出:**

![](img/92e383cf62dd836039c0fba3f7d6d2f8.png)