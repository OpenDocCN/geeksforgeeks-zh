# Python-seaborn的`regplot()`方法

> 原文：[https://www.geeksforgeeks.org/python-seaborn-regplot-method/](https://www.geeksforgeeks.org/python-seaborn-regplot-method/)

`Seaborn`是基于`matplotlib`的Python数据可视化库。它提供了一个高级界面，用于绘制吸引人且信息丰富的统计图形。Seaborn帮助解决了Matplotlib面临的两大问题；问题是：
*   默认Matplotlib参数
*   使用数据框

随着Seaborn对Matplotlib的补充和扩展，学习曲线是相当渐进的。如果你知道Matplotlib，你已经走过了半个Seaborn。

### `seaborn.regplot()`:
该方法用于绘制数据和线性回归模型拟合。有许多互斥的选项来估计回归模型。更多信息[点击此处。](https://www.geeksforgeeks.org/types-of-regression-techniques/)

> **语法:** `seaborn.regplot(x, y, data=None, x_estimator=None, x_bins=None, x_ci='ci', scatter=True, fit_reg=True, ci=95, n_boot=1000, units=None, order=1, logistic=False, lowess=False, robust=False, logx=False, x_partial=None, y_partial=None, truncate=False, dropna=True, x_jitter=None, y_jitter=None, label=None)`
>
> **参数:** 部分主要参数描述如下：
> *   `x, y`: 这些是输入变量。如果是字符串，这些应该与`data`中的列名相对应。当pandas对象被使用时，轴将被标上系列名称。
> *   `data`: 这是数据帧，其中每一列是一个变量，每一行是一个观察值。
> *   `lowess`: (可选) 该参数取布尔值。如果为`True`，则使用`statsmodels`来估计非参数LOWESS模型(局部加权线性回归)。
> *   `color`: (可选) 应用于所有绘图元素的颜色。
> *   `marker`: (可选) 用于散点图字形的标记。
>
> **返回:** 包含绘图的轴对象。

下面是上述方法的实现：

### 示例1
```py
# importing required packages
import seaborn as sns
import matplotlib.pyplot as plt

# loading dataset
data = sns.load_dataset("mpg")

# draw regplot
sns.regplot(x = "mpg",
            y = "acceleration",
            data = data)

# show the plot
plt.show()

# This is contributed
# by Deepanshu Rustagi.
```
**输出:**
![](img/2d5ad0b3c001583b38c5107301e99090.png)

### 示例2
```py
# importing required packages
import seaborn as sns
import matplotlib.pyplot as plt

# loading dataset
data = sns.load_dataset("titanic")

# draw regplot
sns.regplot(x = "age",
            y = "fare",
            data = data,
            dropna = True)
# show the plot
plt.show()

# This is contributed
# by Deepanshu Rustagi.
```
**输出:**
![](img/5e99f40b7894f1614f1260ad852b76ed.png)

### 示例3
```py
# importing required packages
import seaborn as sns
import matplotlib.pyplot as plt

# loading dataset
data = sns.load_dataset("exercise")

# draw regplot
sns.regplot(x = "id",
            y = "pulse",
            data = data)

# show the plot
plt.show()

# This is contributed
# by Deepanshu Rustagi.
```
**输出:**
![](img/d940ccc803fee777309911e4e0c53daf.png)

### 示例4
```py
# importing required packages
import seaborn as sns
import matplotlib.pyplot as plt

# loading dataset
data = sns.load_dataset("attention")

# draw regplot
sns.regplot(x = "solutions",
            y = "score",
            data = data)

# show the plot
plt.show()

# This is contributed
# by Deepanshu Rustagi.
```
**输出:**
![](img/6e7a9eefbcb23c7364d36f6116d00ad8.png)