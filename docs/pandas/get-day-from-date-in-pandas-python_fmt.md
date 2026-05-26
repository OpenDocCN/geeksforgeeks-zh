# 从Pandas日期中提取星期几

> 原文：[https://www.geeksforgeeks.org/get-day-from-date-in-pandas-python/](https://www.geeksforgeeks.org/get-day-from-date-in-pandas-python/)

让我们讨论如何从Pandas的日期中提取星期几。做同样的事情有多种方法。为了更好地理解，让我们借助例子来浏览一下。

## 示例 1

`pandas.date_range`将输入作为日期范围，并返回固定频率的`DatetimeIndex`。`Series.dt.dayofweek`返回一周中从0到6的一天，其中0表示星期一，6表示星期日。

```py
import pandas as pd

date = pd.date_range('2018-12-30', '2019-01-07',
                     freq='D').to_series()
date.dt.dayofweek
```

**输出:**
![](img/9480a9c57f1a6cd6794257110ece71ea.png)

## 示例 2

`pandas.DataFrame`充当`Series`对象的`dict`类型容器。`pandas.to_datetime`将输入转换为`datetime`。

```py
import pandas as pd

date = pd.DataFrame({'inputDate':['2020-07-07']})
date['inputDate'] = pd.to_datetime(date['inputDate'])
date['dayOfWeek'] = date['inputDate'].dt.day_name()

date
```

**输出:**
![](img/799acc83b80a6e27cd2e24f3fa31cdc8.png)

## 示例 3

对于多个输入日期。

```py
import pandas as pd

date = pd.DataFrame({'inputDates':['2015-01-07', '2015-12-02',
                                   '2005-01-03', '2016-11-13',
                                   '2020-06-03'], 
                     'inputVals':[1, 2, 3, 4, 5]})

date['inputDates'] = pd.to_datetime(date['inputDates'])
date['dayOfWeek'] = date['inputDates'].dt.day_name()

date
```

**输出:**

![pandas-day-from-date-1](img/077ceed74eaa44e41a386c748f646397.png)

## 示例 4

为了以特定格式打印日期。

```py
import pandas as pd

date = pd.DataFrame({'inputDates':['1999-7-14', '1998-12-14', 
                                   '2001-01-18', '2020-07-18',
                                   '2006-01-8'], 
                     'inputVals':[1, 2, 3, 4, 5]})

date['inputDates'] = pd.to_datetime(date['inputDates'])
date['dayOfWeek'] = date['inputDates'].dt.dayofweek
days = {0:'Mon', 1:'Tues', 2:'Wed', 3:'Thurs', 4:'Fri', 5:'Sat', 6:'Sun'}
date['dayOfWeek'] = date['dayOfWeek'].apply(lambda x: days[x])

date
```

**输出:**

![pandas-day-from-date-2](img/61901ff148798daa289a6c339b8f5836.png)

## 示例 5

将输入作为日期范围，并打印它们的名称以及给定的数字(0-6)。

```py
import pandas as pd

myDate = pd.DataFrame({'inputDates':list(pd.date_range('2018-12-30',
                                                       '2019-01-07', 
                                                       freq ='D').to_series())})

myDate['inputDates'] = pd.to_datetime(myDate['inputDates'])
myDate['dayOfWeek'] = myDate['inputDates'].dt.dayofweek
myDate['dayOfWeek'] = myDate['inputDates'].dt.day_name()

myDate
```

**输出:**

![python-days-from-date](img/ff6df386aa3ad667916d1d8589761689.png)