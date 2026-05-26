# 如何对熊猫进行多指标分组？

> 原文: [https://www.geeksforgeeks.org/how-to-do-groupby-on-a-multiindex-in-pandas/](https://www.geeksforgeeks.org/how-to-do-groupby-on-a-multiindex-in-pandas/)

在本文中，我们将展示如何在`熊猫`的`多索引`数据框中使用`groupby()`。在数据科学中，当我们执行探索性数据分析时，我们经常使用`groupby()`将一列的数据基于另一列进行分组。因此，我们能够分析一列的数据是如何分组的，或者是如何依赖于另一列的。除了`groupby()`还有一个选择，我们也可以使用`透视表`。

一个`groupby()`操作包括拆分对象、应用函数和组合结果的一些组合。这可用于对这些组中的大量数据和计算操作进行分组。任何`groupby()`操作都涉及对原始数据帧的以下操作之一。它们是：

1.  拆分对象。
2.  组合输出。
3.  应用函数。

> **语法:** `DataFrame.groupby(by=None, axis=0, level=None, as_index=True, sort=True, group_keys=True, squeeze=False, **kwargs)`
>
> **参数**:
>
> *   `by` : 映射、函数、标签或表格列表
> *   `axis` : { 0 或 'index'，1 或 'columns' }，默认 0
> *   `level`: 等级名称
> *   `sort`: 布尔，默认 True
>
> **返回**: 数据帧组比

我们必须将`列表`中的索引名称传递给`groupby()`函数中的`level`参数。‘地区’指数为`level(0)`指数，‘州’指数为`level(1)`指数。在本文中，我们将使用 [**这个**](https://drive.google.com/file/d/1Ir60hFNZfC2Jb08IVE_gjFdk85DlqU5w/view?usp=sharing) CSV 文件。

## 让我们看看 CSV 文件

```py
# importing pandas library 
# as alias pd
import pandas as pd

# storing the data in the df dataframe
# using pandas 'read_csv()'.
df = pd.read_csv('homelessness.csv')

print(df.head())
```

**输出:**

![](img/c8086d9c231678b25191a232b2f9e82b.png)

## 数据框中的列

我们可以通过熊猫`columns`属性知道数据框的列。

```py
# using pandas columns attribute.
col = df.columns

print(col)
```