# 熊猫分组-统计每个组合的出现次数

> 原文：[https://www.geeksforgeeks.org/pandas-groupby-count-the-occurrences-of-each-combination/](https://www.geeksforgeeks.org/pandas-groupby-count-the-occurrences-of-each-combination/)

在本文中，我们将按两列分组，并统计熊猫中每个组合的出现次数。

`DataFrame.groupby()`方法用于将 data frame 分成组。它将生成数据帧的特定列中出现的相似数据计数的数量。

> **语法：**`DataFrame.groupby(by=None, axis=0, level=None)`
>
> **参数：**
>
> - `by`：映射、函数、字符串、标签或可迭代来分组元素。
> - `axis`：按行(`axis=0`)或列(`axis=1`)分组。
> - `level`：整数。按特定级别给组赋值。

为了理解这个概念，我们将使用下面给出的简单数据集：

## Python 3

```py
# Import library
import pandas as pd
import numpy as np

# initialise data of lists.
Data = {'Products':['Box','Color','Pencil','Eraser','Color',
                    'Pencil','Eraser','Color','Color','Eraser','Eraser','Pencil'],

       'States':['Jammu','Kolkata','Bihar','Gujrat','Kolkata',
                 'Bihar','Jammu','Bihar','Gujrat','Jammu','Kolkata','Bihar'],

       'Sale':[14,24,31,12,13,7,9,31,18,16,18,14]}

# Create DataFrame
df = pd.DataFrame(Data, columns=['Products','States','Sale'])

# Display the Output
display(df)
```

**输出：**

![](img/f3dd0f81d8ae1e5accd8aee9e101bbf8.png)

## 方法 1：使用 `DataFrame.size()`

它返回元素的总数，通过将 `shape` 方法返回的行和列相乘进行比较。

> **语法：**`DataFrame.size`

## Python 3

```py
new = df.groupby(['States','Products']).size()
display(new)
```

**输出：**

![](img/4135a5afb7e352472c5e98037df5012c.png)

## 方法 2：使用 `DataFrame.count()`

它用于计算给定轴上非 NA/null 观测值的数量。它也可以处理非浮动类型的数据。

> **语法：**`DataFrame.count(axis=0, level=None, numeric_only=False)`
>
> **参数：**
>
> - `axis`：0 或 `'index'` 表示行方向，1 或 `'columns'` 表示列方向。
> - `level`：如果轴是多索引(分层)，沿着特定级别计数，折叠成数据框。
> - `numeric_only`：仅包含浮点、整数、布尔数据。
>
> **返回：**`count`：Series (或 DataFrame，如果指定了级别)。

## Python 3

```py
new = df.groupby(['States','Products'])['Sale'].count()
display(new)
```

**输出：**

![](img/4135a5afb7e352472c5e98037df5012c.png)

## 方法三：使用 `DataFrame.reset_index()`

这是一种重置数据框索引的方法。`reset_index()`方法将从 0 到数据长度的整数列表设置为索引。

> **语法：**`DataFrame.reset_index(level=None, drop=False, inplace=False, col_level=0, col_fill='')`
>
> **参数：**
>
> - `level`：int、string 或列表，用于从索引中选择和移除传递的列。
> - `drop`：布尔值，如果为假，则将替换的索引列添加到数据中。
> - `inplace`：布尔值，如果为真，则对原始数据框本身进行更改。
> - `col_level`：选择在哪个列级别插入标签。
> - `col_fill`：Object，确定其他关卡的命名方式。
>
> **返回类型：**DataFrame

## Python 3

```py
new = df.groupby(['States','Products'])['Sale'].agg('count').reset_index()
display(new)
```

**输出：**

![](img/0a1d075effc01e0d9d3115ed194fc187.png)

## 方法四：使用 `pandas.pivot()` 功能

它基于数据框的 3 列生成一个透视表。使用索引/列中的唯一值并用值填充。

> **语法：**`pandas.pivot(index, columns, values)`
>
> **参数：**
>
> - `index`【ndarray】：用于制作新帧索引的标签。
> - `columns`【ndarray】：标签用于制作新框架的列。
> - `values`【ndarray】：用于填充新帧值的值。
>
> **返回：**重塑的数据框。
> **异常：**如果有重复，将引发 `ValueError`。

## Python 3

```py
new = df.groupby(['States','Products'],as_index = False
                ).count().pivot('States','Products').fillna(0)
display(new)
```

**输出：**

![](img/5101cb7e953a8299909bd6231de3ea4b.png)