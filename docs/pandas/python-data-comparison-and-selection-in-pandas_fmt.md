# Python Pandas中的数据比较与选择

> 原文：[https://www.geeksforgeeks.org/python-data-comparison-and-selection-in-pandas/](https://www.geeksforgeeks.org/python-data-comparison-and-selection-in-pandas/)

Python 是进行数据分析的优秀语言，主要是因为以数据为中心的 Python 包的奇妙生态系统。`pandas` 就是其中一个包，让导入和分析数据变得容易多了。

## 数据比较

数据分析中最重要的事情是比较值并相应地选择数据。`==` 运算符也适用于 pandas 数据帧中的多个值。下面两个例子将展示如何从 pandas 数据框中比较和选择数据。

要下载使用的 CSV 文件，点击这里 [`employees.csv`](https://media.geeksforgeeks.org/wp-content/uploads/employees.csv)。

### 示例 1：比较数据

在以下示例中，数据帧由 csv 文件制成。在“Gender”栏中，只有 3 种类型的值（“Male”、“Female”或 `NaN`）。性别列的每一行都与“Male”进行比较，然后返回一个布尔序列。

```py
# importing pandas package
import pandas as pd

# making data frame from csv file
data = pd.read_csv("employees.csv")

# storing boolean series in new
new = data["Gender"] == "Male"

# inserting new series in data frame
data["New"]= new

# display
data
```

**输出：**
如输出图像所示，对于 `Gender="Male"`，新列中的值为 `True`，对于“Female”和 `NaN` 值为 `False`。

![](img/02b262732203dda42a44e071aecc8d6f.png)

## 数据选择

### 示例 2：选择数据

在以下示例中，布尔序列被传递给数据，并且仅返回具有 `Gender="Male"` 的行。

```py
# importing pandas package
import pandas as pd

# making data frame from csv file
data = pd.read_csv("employees.csv")

# storing boolean series in new
new = data["Gender"] != "Female"

# inserting new series in data frame
data["New"]= new

# display
data[new]

# OR 
# data[data["Gender"]=="Male"]
# Both are the same
```

**输出：**
如输出图像所示，返回 `Gender="Male"` 的数据帧。

![](img/1850d6c71951284b52db5164650bfea1.png)

**注意：** 对于 `NaN` 值，布尔值为 `False`。