# 如何使用熊猫打印从给定日期开始 n 天的日期？

> 原文：[https://www.geeksforgeeks.org/how-to-print-date-starting-from-the-given-date-for-n-number-of-days-using-pandas/](https://www.geeksforgeeks.org/how-to-print-date-starting-from-the-given-date-for-n-number-of-days-using-pandas/)

在本文中，我们将打印从给定日期开始 n 天的所有日期。可以使用 `pandas.date_range()` 功能完成。该函数用于获取固定频率的日期时间索引。

## 语法

`pandas.date_range(start=None, end=None, periods=None, freq=None, tz=None, normalize=False, name=None, closed=None, **kwargs)`

## 方法

*   导入 `pandas` 模块。
*   创建一个参数函数，用于计算起始日期和期间之间的日期系列。
*   在函数中用 `pandas.date_range()` 生成起始日期和期间之间的日期序列。
*   存储到 `pandas.Series` 内的功能。
*   返回 `pandas.Series`。

下面是实现。

## 代码实现

```python
# Importing modules
import pandas as pd

# creating function
def Time_series(date, per):
    # computing date range with date
    # and given periods
    date_series = pd.date_range(date, periods=per)

    # creating series for date_range
    Result = pd.Series(date_series)
    print(Result)

# Driver Code
# Date in the YYYY-MM-DD format
date = "2020-03-01"

# Number of times the date is
# needed to be printed
per = 10
Time_series(date, per)
```

## 输出

```py
0   2020-03-01
1   2020-03-02
2   2020-03-03
3   2020-03-04
4   2020-03-05
5   2020-03-06
6   2020-03-07
7   2020-03-08
8   2020-03-09
9   2020-03-10
dtype: datetime64[ns]
```