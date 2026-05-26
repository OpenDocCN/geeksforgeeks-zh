# Python | Pandas DatetimeIndex.day

> 原文链接: [https://www.geeksforgeeks.org/python-pandas-dateindex-day/](https://www.geeksforgeeks.org/python-pandas-dateindex-day/)

Python 是进行数据分析的优秀语言，主要是因为以数据为中心的 Python 包的奇妙生态系统。`Pandas` 就是其中一个包，让导入和分析数据变得容易多了。

`Pandas` 的 `DatetimeIndex.day` 属性输出一个索引对象，该对象包含 `DatetimeIndex` 对象的每个条目中的日期。

> **语法：** `DatetimeIndex.day`
>
> **返回:** 包含天数的索引。

## 示例 #1

使用 `DatetimeIndex.day` 属性查找 `DatetimeIndex` 对象中的天数。

```py
# importing pandas as pd
import pandas as pd

# Create the DatetimeIndex
# Here the 'W' represents Weekly frequency
didx = pd.DatetimeIndex(start ='2014-08-01 10:00', freq ='W',
                        periods = 5, tz ='Asia/Calcutta')

# Print the DatetimeIndex
print(didx)
```

**输出:**
![](img/94985781bc59c11062018141674f33bc.png)

现在，我们希望找到 `DatetimeIndex` 对象中存在的所有日期值。

```py
# find all the days present in the object
didx.day
```

**输出:**
![](img/d88947b0701bd820d82b6560fe4bc41f.png)

正如我们在输出中看到的，该函数返回了一个 `Index` 对象，其中包含了 `DatetimeIndex` 对象中每个条目对应的天数值。

## 示例 #2

使用 `DatetimeIndex.day` 属性查找 `DatetimeIndex` 对象中存在的天数。

```py
# importing pandas as pd
import pandas as pd

# Create the DatetimeIndex
# Here the 'M' represents Month end frequency
didx = pd.DatetimeIndex(start ='2014-08-01 10:00', freq ='M',
                        periods = 5, tz ='Asia/Calcutta')

# Print the DatetimeIndex
print(didx)
```

**输出:**
![](img/6a4d50abdb4e92376b9420296aed9b33.png)

现在，我们希望找到 `DatetimeIndex` 对象中存在的所有日期值。

```py
# find all the months in the object
didx.day
```

**输出:**
![](img/d1990a8ffbdae2bd523c75e635089347.png)

正如我们在输出中看到的，函数返回了一个 `Index` 对象，其中包含了 `DatetimeIndex` 对象中每个条目对应的天数值。