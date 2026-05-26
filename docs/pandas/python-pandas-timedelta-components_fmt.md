# Python Pandas Timedelta 组件

> 原文：[https://www.geeksforgeeks.org/python-pandas-timedelta-components/](https://www.geeksforgeeks.org/python-pandas-timedelta-components/)

Python 是进行数据分析的优秀语言，主要是因为以数据为中心的 python 包的奇妙生态系统。Pandas 就是其中之一，它让数据的导入和分析变得更加容易。

时间增量是 `datetime.timedelta` 的一个子类，并且以类似的方式表现。它相当于 Python 的 `datetime.timedelta`，在大多数情况下可以互换。`pandas.Timedelta` 中的 `Timedelta.components` 属性用于返回一个名为 `components` 的类。

## 语法
`Timedelta.components`

## 参数
无

## 返回
返回一个名为 `components` 的类。

### 代码#1
```py
# importing pandas as pd 
import pandas as pd

# Create the Timedelta object 
td = pd.Timedelta('3 days 06:05:01.000030')

# Print the Timedelta object 
print(td)

print(td.components)
```

**Output:**
> 3 天 06:05:01.000030
> components(days=3, hours=6, minutes=5, seconds=1, milliseconds=0, microseconds=30, nanoseconds=0)

### 代码#2
```py
# importing pandas as pd 
import pandas as pd

# Create the Timedelta object 
td = pd.Timedelta('1 days 7 hours')

# Print the Timedelta object 
print(td)

print(td.components)
```

**Output:**
> 1 天 07:00:00
> components(days=1, hours=7, minutes=0, seconds=0, milliseconds=0, microseconds=0, nanoseconds=0)

### 代码#3
```py
# importing pandas as pd 
import pandas as pd 
import datetime

# Create the Timedelta object 
td = pd.Timedelta(datetime.timedelta(days = 3, hours = 7, seconds = 8))

# Print the Timedelta object 
print(td)

print(td.components)
```

**Output:**
> 3 天 07:00:08
> components(days=3, hours=7, minutes=0, seconds=8, milliseconds=0, microseconds=0, nanoseconds=0)