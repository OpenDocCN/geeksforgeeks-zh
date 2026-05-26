# 绘制熊猫中一组对象中每组的大小

> 原文: [https://www.geeksforgeeks.org/plot-the-size-of-each-group-in-a-groupby-object-in-pandas/](https://www.geeksforgeeks.org/plot-the-size-of-each-group-in-a-groupby-object-in-pandas/)

`pandas`库中的`DataFrame.groupby()`函数是最有用的函数之一，它根据列/条件将数据分成组，然后应用一些操作，例如`size()`，计算每个组中的条目/行数。`groupby()`也可以应用于系列。

> **语法:** `DataFrame.groupby(by=None, axis=0, level=None, as_index=True, sort=True, group_keys=True, squeeze=False, **kwargs)`
> **参数:**
> **by :** 映射、函数、str 或可迭代
> **axis :** int，缺省值 0
> **level :** 如果 axis multi index(分层)，则按特定级别或仅与数据帧输入相关。`as_index=False` 实际上是“SQL 风格”的分组输出
> **sort:** 排序组键。关闭此功能可以获得更好的性能。请注意，这不会影响各组内的观察顺序。`groupby` 保留每个组中的行顺序。
> **group_keys :** 调用 `apply` 时，将组合键添加到索引中以识别片段
> **squeeze:** 如果可能，减少返回类型的维数，否则返回一致类型
> **返回:** `GroupBy` 对象

在下面的例子中，我们将使用两个库`seaborn`和`pandas`，其中`seaborn`用于绘图，`pandas`用于读取数据。我们将使用 `seaborn` 的`load_dataset()`方法来加载`penguins.csv`数据集。

## 加载数据

```py
# import the module
import seaborn as sns
dataset = sns.load_dataset('penguins')

# displaying the data
print(dataset.head())
```

**输出:**

![](img/7cc2a2cf049a2fc4382dd6378a34cb2c.png)

数据集的前五行

## 查看数据信息

使用`info()`方法获得更多关于数据集的信息。

```py
# display the number of columns and their data types
dataset.info()
```

**输出:**

![](img/3d819d09537df3fb6af2b627f8e23752.png)

关于数据集的信息

## 分组与绘图

我们将根据`island`使用`groupby()`方法对数据进行分组并绘制。

### 使用 pandas 绘图

```py
# apply groupby on the island column
# plotting
dataset.groupby(['island']).size().plot(kind = "bar")
```

![](img/1c66ffa4b4326e839b0e02ffb9dab7f6.png)

使用 pandas 绘制 `groupby()` 大小的图

### 使用 seaborn 绘图

```py
# use the groupby() function to group island column
# and apply size() function
# size() is equivalent to counting the distinct rows
result = dataset.groupby(['island']).size()

# plot the result
sns.barplot(x = result.index, y = result.values)
```

![](img/bd1df1325d5101440723acd5c7f46ab0.png)

使用 seaborn 绘制尺寸图