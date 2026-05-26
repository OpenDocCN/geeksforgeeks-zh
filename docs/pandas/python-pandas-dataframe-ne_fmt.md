# pandas DataFrame.ne()

> 原文链接: https://www.geeksforgeeks.org/python-pandas-dataframe-ne/

Python 是进行数据分析的优秀语言，主要是因为以数据为中心的 Python 包的奇妙生态系统。`pandas` 就是其中一个包，让导入和分析数据变得容易多了。
`pandas` 的 `DataFrame.ne()` 函数检查数据帧元素与常量、序列或其他数据帧元素之间的不相等性。如果比较中的两个值不相等，则返回 `True`，否则返回 `False`。

> **语法:** `DataFrame.ne(other, axis='columns', level=None)`
> **参数:**
> - `other` : Series, DataFrame, 或常量
> - `axis` : 对于 Series 输入，axis 要匹配
> - `level` : 跨级别广播，匹配传递的 MultiIndex 级别上的索引值
> **返回:** 结果: DataFrame

**示例 1:** 使用 `ne()` 函数检查数列和数据框之间的不等式。

## Python 3

```py
# importing pandas as pd
import pandas as pd

# Creating the first dataframe
df1=pd.DataFrame({"A":[14,4,5,4,1],
                  "B":[5,2,54,3,2],
                  "C":[20,20,7,3,8],
                  "D":[14,3,6,2,6]})

# Print the dataframe
df1
```

![](img/e2afe8b153c85cb1bf5c21ff28fd66d2.png)

让我们创建系列。

## Python 3

```py
# importing pandas as pd
import pandas as pd

# create series
sr = pd.Series([3, 2, 4, 5, 6])

# Print series
sr
```

![](img/7f840a7c7890ecd2fd925978f337304e.png)

让我们使用 `DataFrame.ne()` 函数来计算不等式。

## Python 3

```py
# evaluate inequality over the index axis
df1.ne(sr, axis = 0)
```

**输出:**

![](img/19ae2525a6dafad7e3dc4ec9bdf02784.png)

所有 `True` 值单元格表示比较值彼此不相等，而所有 `False` 值单元格表示比较值彼此相等。

**示例 2:** 使用 `ne()` 函数检查两个数据帧的不相等性。一个数据帧包含数值。

## Python 3

```py
# importing pandas as pd
import pandas as pd

# Creating the first dataframe
df1=pd.DataFrame({"A":[14,4,5,4,1],
                  "B":[5,2,54,3,2],
                  "C":[20,20,7,3,8],
                  "D":[14,3,6,2,6]})

# Creating the second dataframe with NaN value
df2=pd.DataFrame({"A":[12,4,5,None,1],
                  "B":[7,2,54,3,None],
                  "C":[20,16,11,3,8],
                  "D":[14,3,None,2,6]})

# Print the second dataframe
df2
```

![](img/53cd7ef7a1eb5f4a9f64d1d7263e2ac1.png)

让我们使用 `DataFrame.ne()` 函数。

## Python 3

```py
# passing df2 to check for inequality with the df1 dataframe.
df1.ne(df2)
```

**输出:**

![](img/af8e433864393a484bd71904cf62e317.png)

所有 `True` 值单元格表示比较值彼此不相等，而所有 `False` 值单元格表示比较值彼此相等。