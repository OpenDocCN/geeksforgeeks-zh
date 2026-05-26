# Python | Pandas DataFrame.count()

> 原文: [https://www.geeksforgeeks.org/python-pandas-dataframe-count/](https://www.geeksforgeeks.org/python-pandas-dataframe-count/)

Python 是进行数据分析的优秀语言，主要是因为以数据为中心的 python 包的奇妙生态系统。`Pandas` 就是其中一个包，让导入和分析数据变得容易多了。

`DataFrame.count()` 用于计算给定轴上非 NA/null 观测值的数量。它也可以处理非浮动类型的数据。

## 语法
`DataFrame.count(axis=0, level=None, numeric_only=False)`

## 参数
- `axis`: 0 或 `'index'` 代表行，1 或 `'columns'` 代表列。
- `level`: 如果轴是多索引（分层），沿特定级别计数，折叠成数据框。
- `numeric_only`: 仅包括浮点、int、布尔数据。

## 返回
`count`: Series（或 DataFrame，如果指定了级别）。

## 示例 #1
使用 `count()` 函数查找行轴上非 NA/null 值的数量。

```py
# importing pandas as pd
import pandas as pd

# Creating a dataframe using dictionary
df = pd.DataFrame({"A":[-5, 8, 12, None, 5, 3], 
                   "B":[-1, None, 6, 4, None, 3],
                   "C":["sam", "haris", "alex", np.nan, "peter", "nathan"]})

# Printing the dataframe
df
```

![](img/84ce0e8897107bd293fce05c647deb46.png)

现在，请找出行轴上非数值的计数。

```py
# axis = 0 indicates row
df.count(axis = 0)
```

**输出:**
![](img/bd2bcd8380da9639afd78bf6669e2170.png)

## 示例 #2
使用 `count()` 函数查找跨列的非 NA/null 值的个数。

```py
# importing pandas as pd
import pandas as pd

# Creating a dataframe using dictionary
df = pd.DataFrame({"A":[-5, 8, 12, None, 5, 3],
                   "B":[-1, None, 6, 4, None, 3], 
                   "C":["sam", "haris", "alex", np.nan, "peter", "nathan"]})

# Find count of non-NA across the columns
df.count(axis = 1)
```

**输出:**
![](img/1f447705aa323fde656ccaa6bf130b6f.png)