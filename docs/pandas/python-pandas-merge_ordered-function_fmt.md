# Python: pandas.merge_ordered()函数

> 原文: [https://www.geeksforgeeks.org/python-pandas-merge_ordered-function/](https://www.geeksforgeeks.org/python-pandas-merge_ordered-function/)

这种方法用于设计有序数据，如时间序列数据。可选地执行分组合并。

> **语法:** `pandas.merge_ordered(left, right, on=None, left_on=None, right_on=None, left_by=None, right_by=None, fill_method=None, suffixes=('_x', '_y'), how='outer')`
>
> **参数:**
>
> *   `left`: 数据框
> *   `right`: 数据框
> *   `on`: 标签或列表上
> *   `left_on`: 标签或列表，或类似数组
> *   `right_on`: 标签或列表，或类似数组
> *   `left_by`: 列名或列名列表
> *   `right_by`: 列名或列名列表
> *   `fill_method`: `{'ffill', None}`，默认 `None`
> *   `suffixes`: 列表式，默认为 `("_x", "_y")`
> *   `how`: `{'left', 'right', 'outer', 'inner'}`，默认 `'outer'`
>
> **返回:** 一个数据帧，其中合并的数据帧输出类型将与 `left` 相同，如果它是数据帧的子类。

## 示例 1：合并具有相同元素数量的有序两个数据帧

```py
# importing the module
import pandas as pd

# creating the first DataFrame
df1 = pd.DataFrame({
    "date": ['2007-02-01', '2007-03-01', '2007-04-01', '2007-05-01', '2007-06-01'],
    "close": [12.08, 13.27, 14.27, 17.31, 17.43]
})
print("The first DataFrame")
print(df1)

# creating the second DataFrame
df2 = pd.DataFrame({
    "date": ['2007-01-01', '2007-02-01', '2007-03-01', '2007-04-01', '2007-05-01'],
    "close": [44.34, 43.68, 45.04, 48.27, 50.54]
})
print("The second DataFrame")
print(df2)

# merging the DataFrames
print("The merge_ordered DataFrame")

df = pd.merge_ordered(df1, df2, on='date', suffixes=('_df1', '_df2'))

print(df)
# This code is contributed by rakeshsahni
```

**输出:**

![](img/476635365a464529f4c592762d19edaf.png)

## 示例 2：用之前的值填充缺失的部分

我们使用 `fill_method = 'ffill'` (向前填充)

```py
# importing the module
import pandas as pd

# creating the first DataFrame
df1 = pd.DataFrame({
    "date": ['2007-02-01', '2007-03-01', '2007-04-01', '2007-05-01', '2007-06-01'],
    "close": [12.08, 13.27, 14.27, 17.31, 17.43]
})
print("The first DataFrame")
print(df1)

# creating the second DataFrame
df2 = pd.DataFrame({
    "date": ['2007-01-01', '2007-02-01', '2007-03-01', '2007-04-01', '2007-05-01'],
    "close": [44.34, 43.68, 45.04, 48.27, 50.54]
})
print("The second DataFrame")
print(df2)

# merging the DataFrames
print("The merge_ordered DataFrame")

df = pd.merge_ordered(df1, df2, on='date', suffixes=(
    '_df1', '_df2'), fill_method='ffill')

print(df)
# This code is contributed by rakeshsahni
```

**输出:**

![](img/7cd6664dd93344e35810b99cc06c29cc.png)

## 示例 3：使用 `left_by` 参数分组合并

我们将使用 `left_by` 参数，该参数将左侧数据框按组列分组，并与右侧数据框逐块合并。

```py
# importing the module
import pandas as pd

# creating the first DataFrame
df1 = pd.DataFrame(
    {
        "key": ["k1", "k3", "k5", "k1", "k3", "k5"],
        "value1": [1, 2, 3, 1, 2, 3],
        "gp": ["g1", "g1", "g1", "g2", "g2", "g2"]
    }
)
df1
print("The first DataFrame")
print(df1)

# creating the second DataFrame
df2 = pd.DataFrame({"key": ["k2", "k3", "k4"], "value2": [1, 2, 3]})

print("The second DataFrame")
print(df2)

# merging the DataFrames
print("The merge_ordered DataFrame")

df = pd.merge_ordered(df1,df2,fill_method='ffill',left_by="gp")

print(df)
# This code is contributed by rakeshsahni
```

**输出:**

![](img/6e7bcb643b40573e7aed619675602a0f.png)