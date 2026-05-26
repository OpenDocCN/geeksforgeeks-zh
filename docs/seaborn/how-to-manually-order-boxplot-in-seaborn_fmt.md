# 如何在 Seaborn 中手动排序箱线图？

> 原文：[https://www.geeksforgeeks.org/how-to-manually-order-boxplot-in-seaborn/](https://www.geeksforgeeks.org/how-to-manually-order-boxplot-in-seaborn/)

[**Seaborn**](https://www.geeksforgeeks.org/introduction-to-seaborn-python/) 是一个用于 Python 统计图形绘制的出色可视化库。它提供了漂亮的默认样式和调色板，使统计图更具吸引力。它建立在 [matplotlib](https://www.geeksforgeeks.org/python-introduction-matplotlib/) 库的基础上，并与 [pandas](https://www.geeksforgeeks.org/introduction-to-pandas-in-python/) 的数据结构紧密结合。
Seaborn 旨在通过可视化探索和理解数据的核心部分。它提供了面向数据集的 API，因此我们可以在相同变量的不同视觉表示之间切换，以便更好地理解数据集。

**箱线图**是通过四分位数描绘数字数据组的视觉表示。箱线图也用于检测数据集中的异常值。它通过一个简单的方框和触须高效地捕获数据摘要，并允许我们轻松地跨组进行比较。箱线图使用第 25、50 和 75 个百分位数汇总样本数据。这些百分位数也被称为下四分位数、中位四分位数和上四分位数。

在本文中，我们将讨论如何手动排序箱线图。

## 使用的数据集

下例中使用的数据集是：[https://www.kaggle.com/ranjeetjain3/seaborn-tips-dataset](https://www.kaggle.com/ranjeetjain3/seaborn-tips-dataset)

## 逐步方法

### 1. 导入库

```python
# import required modules
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

### 2. 加载数据集

```python
# load dataset
tips = sns.load_dataset('tips')

# display top most rows
tips.head()
```

**输出：**

![](img/17da73e436efda34c1a0ded830f16140.png)

### 3. 画出方框图

```python
# illustrate box plot
fx = sns.boxplot(x='day', y='total_bill', data=tips, hue='sex', palette='Set2')
```

**输出：**

![](img/eacc8167d0abd113b575973e559dff1f.png)

### 4. 使用 `order` 参数绘制箱线图

请看上图的顺序和根据我们的需要设置顺序后的区别。调色板将改变图形的颜色（您也可以尝试 `Set1` 和 `Set3`）。

```python
# illustrating box plot with order
fx = sns.boxplot(x='day', y='total_bill', data=tips, order=[
                 'Sun', 'Sat', 'Fri', 'Thur'], hue='sex', palette='Set2')
```

**输出：**

![](img/c828d1a8d03565f9d941584691fbc8c8.png)

### 5. 两张图对比

![](img/2a61aa3f96eb39c21bd6fdd46bacafce.png) ![](img/6247f3f59bc0834ead30d3f845a73e1a.png)

## 完整程序示例

### 例 1

```python
# import required modules
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# load dataset
tips = sns.load_dataset('tips')

# display top most rows
tips.head()

# illustrating box plot with order
sns.boxplot(x='day', y='total_bill', data=tips, order=[
            'Sun', 'Sat', 'Fri', 'Thur'], hue='sex', palette='Set2')
```

**输出：**

![](img/cc55583ced8d148327caa2b996f46e19.png)

### 例 2

现在，使用不同的特征绘制箱线图。注意下图中 x 轴上的顺序：

```python
# import required modules
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# load dataset
tips = sns.load_dataset('tips')

# display top most rows
tips.head()

# plotting the boxplot taking time on x-axis
fx = sns.boxplot(x="time", y="total_bill", hue="smoker",
                 data=tips, palette="Set1")

# illustrating box plot with order
ax = sns.boxplot(x="time", y="total_bill", hue="smoker", order=['Dinner', 'Lunch'],
                 data=tips, palette="Set1")
```

**输出：**

- 排序前：

![](img/9d85f20ef723b17455e3a1f468b5fc56.png)

- 排序后：

![](img/dc008214303212f678590ab62391e516.png)

这里我们已经手动排序了箱线图。