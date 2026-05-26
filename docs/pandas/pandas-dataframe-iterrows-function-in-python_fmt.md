# Pandas DataFrame.iterrows() 函数详解

> 原文：[https://www.geeksforgeeks.org/pandas-dataframe-iterrows-function-in-python/](https://www.geeksforgeeks.org/pandas-dataframe-iterrows-function-in-python/)

`Pandas DataFrame.iterrows()` 用于以 (索引, 序列) 对的形式迭代 Pandas DataFrame 行。这个函数遍历数据框列，它将返回一个元组，该元组的列名和内容以序列的形式出现。

> **语法：** `DataFrame.iterrows()`
>
> **收益率：**
> - `index` - 该行的索引。多索引的元组。
> - `data` - 作为 Series 的行数据。
>
> **返回：**
> - `it`：一个遍历框架行的生成器。

## 示例 1

有时我们需要在不使用任何循环的情况下遍历数据框的行和列，在这种情况下，`Pandas DataFrame.iterrows()` 起着至关重要的作用。

```py
import pandas as pd

# Creating a data frame along with column name
df = pd.DataFrame([[2, 2.5, 100, 4.5, 8.8, 95]], columns=[
                  'int', 'float', 'int', 'float', 'float', 'int'])

# Iter over the data frame rows
# using df.iterrows()
itr = next(df.iterrows())[1]
itr
```

**输出：**

![](img/5e4ae99f848b0e28004c8e1ddf4f6030.png)

在上面的例子中，我们使用 `Pandas DataFrame.iterrows()` 对数字数据帧行进行迭代。

## 示例 2

```py
import pandas as pd

# Creating a data frame
df = pd.DataFrame([['Animal', 'Baby', 'Cat', 'Dog',
                    'Elephant', 'Frog', 'Gragor']])

# Itering over the data frame rows
# using df.iterrows()
itr = next(df.iterrows())[1]
itr
```

**输出：**

![](img/6bafa5f506704257319b8e70baf6ef28.png)

在上面的例子中，我们使用 `Pandas DataFrame.iterrows()` 对没有列名的数据帧进行迭代。

**注意：** 由于 `iterrows` 为每行返回一个 Series，因此**不会跨行保留**数据类型。