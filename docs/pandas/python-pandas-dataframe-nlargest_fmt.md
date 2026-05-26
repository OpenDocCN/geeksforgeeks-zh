# Python | Pandas DataFrame.nlargest()

> 原文: [https://www.geeksforgeeks.org/python-pandas-dataframe-nlargest/](https://www.geeksforgeeks.org/python-pandas-dataframe-nlargest/)

Python 是进行数据分析的优秀语言，主要是因为以数据为中心的 Python 包的奇妙生态系统。`Pandas` 就是其中一个包，让导入和分析数据变得容易多了。

`Pandas` 的 `nlargest()` 方法用于从一个数据帧或一个序列中获取 n 个最大值。

**语法:**

```py
DataFrame.nlargest(n, columns, keep='first')
```

**参数:**

> **n:** int，要选择的值的数量
> **columns:** 列检查值，或者用户也可以在调用时选择列。[例如: `data["Age"].nlargest(3)` 或 `data.nlargest(3, "Age")`]
> **keep:** 对象以设置在重复项退出时选择哪个值。选项是 `'first'` 或 `'last'`

要下载使用的 CSV 文件，点击这里 [employees.csv](https://media.geeksforgeeks.org/wp-content/uploads/employees.csv)。

**代码#1:** 提取最大 5 个值
在本例中，提取最大 5 个值，然后与 `sort_values()` 函数排序的其他值进行比较。在尝试此方法之前，会移除 `NaN` 值。

参考 [`sort_values()`](https://www.geeksforgeeks.org/python-pandas-dataframe-sort_values-set-1/) 和 [`dropna()`](https://www.geeksforgeeks.org/python-pandas-dataframe-dropna/) 功能。

```py
# importing pandas package
import pandas as pd

# making data frame from csv file
data = pd.read_csv("employees.csv")

# removing null values
data.dropna(inplace = True)

# extracting greatest 5
large5 = data.nlargest(5, "Salary")

# display
large5
```

**输出:**
![](img/b9ae112a0cfe92b3a061cafb831ecfb7.png)

**代码#2:** 按 `sort_values()` 排序

```py
# importing pandas package
import pandas as pd

# making data frame from csv file
data = pd.read_csv("employees.csv")

# removing null values
data.dropna(inplace = True)

# sorting in descending order
data.sort_values("Salary", ascending = False, inplace = True)

# displaying top 5 values
data.head()
```

**输出:**

如输出图像所示，两个函数返回的值相似。
![](img/4f421b28de51da47069c359076fb06d7.png)