# Pandas.melt()函数详解

> 原文：[https://www.geeksforgeeks.org/python-pandas-melt/](https://www.geeksforgeeks.org/python-pandas-melt/)

为了更容易地分析表格中的数据，我们可以使用 Python 中的 Pandas 将数据重塑为更便于计算机使用的形式。`pandas.melt()` 就是这样一个功能。
`pandas.melt()` 将数据框从宽格式取消固定为长格式。
`melt()` 函数用于将数据框转换为一种格式，其中一列或多列是标识符变量，而所有其他被认为是测量变量的列被取消固定到行轴，只留下两个非标识符列，`variable` 和 `value`。

## 语法

```py
pandas.melt(frame, id_vars=None, value_vars=None,
 var_name=None, value_name='value', col_level=None)
```

## 参数说明

- `frame`：数据框。
- `id_vars`：元组、列表或数组，可选。用作标识符变量的列。
- `value_vars`：元组、列表或数组，可选。要取消固定的列。如果未指定，将使用所有未设置为 `id_vars` 的列。
- `var_name`：标量。用于“变量”列的名称。如果没有，则使用 `frame.columns.name` 或 `'variable'`。
- `value_name`：标量，默认 `'value'`。用于‘值’列的名称。
- `col_level`：int 或 string，可选。如果列是多索引，则使用该级别进行熔化。

## 使用示例

创建一个简单的数据框。

```py
# importing pandas as pd
import pandas as pd

# creating a dataframe
df = pd.DataFrame({'Name': {0: 'John', 1: 'Bob', 2: 'Shiela'},
                   'Course': {0: 'Masters', 1: 'Graduate', 2: 'Graduate'},
                   'Age': {0: 27, 1: 23, 2: 21}})
df
```

![](img/e96f8ddc53c7296c8afc91d730e4f0da.png)

将 `Name` 作为 `id_vars`，`Course` 作为 `value_vars`。

```py
pd.melt(df, id_vars =['Name'], value_vars =['Course'])
```

![](img/0fb120872572f2e51a771fa8dbe0cfdf.png)

取消固定多个列。

```py
pd.melt(df, id_vars =['Name'], value_vars =['Course', 'Age'])
```

![](img/d284c5972cb8f85e98e83fc3c63ef2ab.png)

自定义 `variable` 和 `value` 列的名称。

```py
pd.melt(df, id_vars =['Name'], value_vars =['Course'],
              var_name ='ChangedVarname', value_name ='ChangedValname')
```

![](img/15aa9c4872e232b46d13e311a506cbc1.png)