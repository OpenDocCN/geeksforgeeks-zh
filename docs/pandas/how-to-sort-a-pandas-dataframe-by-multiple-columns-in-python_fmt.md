# 如何在 Python 中对熊猫数据帧进行多列排序？

> 原文：[https://www.geeksforgeeks.org/how-to-sort-a-pandas-dataframe-by-multiple-columns-in-python/](https://www.geeksforgeeks.org/how-to-sort-a-pandas-dataframe-by-multiple-columns-in-python/)

排序是基于条件要求对数据帧执行的操作之一。我们可以按字母顺序以及数字顺序对数据帧进行排序。在本文中，我们将看到如何按多列对熊猫数据框进行排序。

## 方法 1：使用 `sort_values()` 方法

> **语法：** `df_name.sort_values(by, axis=0, ascending=True, inplace=False, kind='quicksort', na_position='last', ignore_index=False, key=None)`
>
> **参数：**
>
> - `by`：它应该排序的列表或列的名称。
> - `axis`：待排序轴。（`0` 或 `'index'`，`1` 或 `'columns'`）默认为 `0`。
> - `ascending`：排序升序或降序。为多个排序顺序指定布尔值列表。布尔值列表必须与 `by` 的值的数量相匹配，即列名。默认情况下，这是 `True`。
> - `inplace`：默认为 `False`。但是如果它的值为 `True`，它就地即在适当的位置执行操作。
> - `kind`：选择快速排序等排序算法。合并排序，堆排序。默认情况下，它是 `'quicksort'`。

## 对数据帧进行排序

1.  导入模块。
2.  创建一个数据帧。
3.  现在，使用上面的语法对数据帧进行排序。

### 创建数据帧

```python
#import libraries
import numpy as np
import pandas as pd

# creating a dataframe
df = pd.DataFrame({'Name': ['Raj', 'Akhil', 'Sonum', 'Tilak', 'Divya', 'Megha'],
                   'Age': [20, 22, 21, 19, 17, 23],
                   'Rank': [1, np.nan, 8, 9, 4, np.nan]})

# printing the dataframe
print('DATAFRAME')
df
```

**输出：**

![](img/2350c97bd67a40127dd0512ad7c74062.png)

### 例 1

```python
# using the sorting function
print('SORTED DATAFRAME')
df.sort_values(by=['Age'], ascending=False)
```

**输出：**

![](img/91f37d53193a7e92b00f38e030fc1a7a.png)

在上面的示例中，`ascending` 值为 `False`，因此数据帧按降序排序。

### 例 2

```python
print('SORTED DATAFRAME')
df.sort_values(by = ['Rank', 'Age'], ascending = [True, False], na_position = 'first')
```