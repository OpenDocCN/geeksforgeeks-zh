# Python Pandas: `df.size`, `df.shape`, 和 `df.ndim`

> 原文: [https://www.geeksforgeeks.org/python-pandas-df-size-df-shape-and-df-ndim/](https://www.geeksforgeeks.org/python-pandas-df-size-df-shape-and-df-ndim/)

Python 是进行数据分析的优秀语言，主要是因为以数据为中心的 Python 包的奇妙生态系统。`Pandas` 就是其中一个包，让导入和分析数据变得容易多了。

`Pandas` 的 `.size`、`.shape` 和 `.ndim` 用于返回 `DataFrame` 和 `Series` 的大小、形状和维度。

> **语法:** `DataFrame.size`
> **返回:** 返回 `DataFrame`/`Series` 的大小，等于元素总数。也就是行 x 列。
>
> **语法:** `DataFrame.shape`
> **返回:** 返回 `DataFrame`/`Series` 的形状（行、列）元组。
>
> **语法:** `DataFrame.ndim`
> **返回:** 返回 `DataFrame`/`Series` 的维度。一维（`Series`）为 1，二维（`DataFrame`）为 2。

要下载下例使用的数据集，点击[这里](https://media.geeksforgeeks.org/wp-content/uploads/nba.csv)。

在下面的例子中，使用的 `DataFrame` 包含了一些 NBA 球员的数据。任何操作前的 `DataFrame` 图像附在下面。
![](img/793ad040c852f46d3cbfdaf19ee388c2.png)

### 示例:
在本例中，首先存储大小和形状的输出。由于 `.size` 返回元素总数，所以通过 `shape` 方法返回的行和列相乘进行比较。之后，还使用 `.ndim` 检查 `DataFrame` 和 `Series` 的维度。

```py
# importing pandas module
import pandas as pd

# making data frame
data = pd.read_csv("https://media.geeksforgeeks.org/wp-content/uploads/nba.csv")

# dataframe.size
size = data.size

# dataframe.shape
shape = data.shape

# dataframe.ndim
df_ndim = data.ndim

# series.ndim
series_ndim = data["Salary"].ndim

# printing size and shape
print("Size = {}\nShape ={}\nShape[0] x Shape[1] = {}".
format(size, shape, shape[0]*shape[1]))

# printing ndim
print("ndim of dataframe = {}\nndim of series ={}".
format(df_ndim, series_ndim))
```

### 输出:

```py
Size = 4122
Shape=(458, 9)
Shape[0] x Shape[1] = 4122
ndim of dataframe = 2
ndim of series=1
```

可以看出，行 x 列来自 `.shape` 等于 `.size`。
同样，`DataFrame` 的 `ndim` 为 2，`Series` 为 1，这适用于所有类型的 `DataFrame` 和 `Series`。