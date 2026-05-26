# pandas DataFrame.quantile()

> 原文: [https://www.geeksforgeeks.org/python-pandas-dataframe-quantile/](https://www.geeksforgeeks.org/python-pandas-dataframe-quantile/)

Python 是进行数据分析的优秀语言，主要是因为以数据为中心的 python 包的奇妙生态系统。Pandas 就是其中一个包，让导入和分析数据变得容易多了。

`dataframe.quantile()` 函数返回所请求轴上给定分位数的值，即一个数值百分比。

**注：** 在将频率分布分成相等组的变量的任何一组值中，每个组包含总人口的相同部分。

## 语法与参数

**语法：** `DataFrame.quantile(q=0.5, axis=0, numeric_only=True, interpolation='linear')`

**参数：**

- **q：** 浮点数或类数组，默认 0.5 (50%分位数)。`0 <= q <= 1`，计算分位数。
- **axis：** `[{0, 1, 'index', 'columns'}]` (默认为 0)。行方向为 0 或 `'index'`，列方向为 1 或 `'columns'`。
- **numeric_only：** 如果为 `False`，也将计算日期时间和时间增量数据的分位数。
- **interpolation：** `{"linear", "lower", "higher", "midpoint", "nearest"}`

**返回：** 分位数：Series 或 DataFrame

- 如果 `q` 是数组，将返回一个 DataFrame，其中索引是 `q`，列是自身的列，值是分位数。
- 如果 `q` 是浮点数，将返回一个 Series，其中索引是 `self` 的列，值是分位数。

## 示例

### 示例 1：使用 `quantile()` 函数找到 0.2 分位数的值

```py
# importing pandas as pd
import pandas as pd

# Creating the dataframe 
df = pd.DataFrame({"A":[1, 5, 3, 4, 2],
                   "B":[3, 2, 4, 3, 4],
                   "C":[2, 2, 7, 3, 4], 
                   "D":[4, 3, 6, 12, 7]})

# Print the dataframe
df
```

![](img/f81d9e7664bffaa4d6e99e24c210142e.png)

让我们使用 `dataframe.quantile()` 函数来为数据帧中的每一列找到 0.2 的分位数。

```py
# find the product over the index axis
df.quantile(.2, axis = 0)
```

**输出：**
![](img/a573662d0fd930252cb1398e357339cc.png)

### 示例 2：使用 `quantile()` 函数沿索引轴查找 (0.1, 0.25, 0.5, 0.75) 分位数。

```py
# importing pandas as pd
import pandas as pd

# Creating the dataframe 
df = pd.DataFrame({"A":[1, 5, 3, 4, 2],
                   "B":[3, 2, 4, 3, 4],
                   "C":[2, 2, 7, 3, 4],
                   "D":[4, 3, 6, 12, 7]})

# using quantile() function to
# find the quantiles over the index axis
df.quantile([.1, .25, .5, .75], axis = 0)
```

**输出：**
![](img/4d1efb869fda77719bbfbb14f86269ec.png)