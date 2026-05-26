# Panel.cumprod()函数详解

> 原文:[https://www.geeksforgeeks.org/python-pandas-panel-cumprod/](https://www.geeksforgeeks.org/python-pandas-panel-cumprod/)

## 面板数据容器介绍

在熊猫中，面板是一个非常重要的三维数据容器。三个轴的名称旨在为描述涉及面板数据的操作，特别是面板数据的计量经济学分析提供一些语义含义。

`Panel.cumprod()`函数用于返回包含累计乘积的相同大小的数据帧或系列。

> **语法:** `Panel.cumprod(axis=None, skipna=True, *args, **kwargs)`
>
> **参数:**
> **axis:** 轴的索引或名称。0 相当于`None`或`'index'`。
> **skipna:** 排除 NA/null 值。如果整行/整列为`None`，结果将为`None`。
>
> **返回:** 数据框或面板的成品

## 代码示例

**代码#1:**

```py
# importing pandas module
import pandas as pd
import numpy as np

df1 = pd.DataFrame({'a': ['Geeks', 'For', 'geeks', 'for', 'real'],
                    'b': [11, 1.025, 333, 114.48, 1333]})

data = {'item1':df1, 'item2':df1}

# creating Panel
panel = pd.Panel.from_dict(data, orient ='minor')

print(panel['b'])

print("\n", panel['b'].cumprod(axis = 0))
```

**输出:**
![](img/6a1d045867a9a42779b9c24c11e3570b.png)

**代码#2:**

```py
# importing pandas module
import pandas as pd
import numpy as np

df1 = pd.DataFrame({'a': ['Geeks', 'For', 'geeks'],
                    'b': np.random.randn(3)})

data = {'item1':df1, 'item2':df1}

# creating Panel
panel = pd.Panel.from_dict(data, orient ='minor')

print(panel['b'])

print("\n", panel['b'].cumprod(axis = 0))
```

**输出:**
![](img/8c98d96a324fd426e47aab3e1fbc80e7.png)