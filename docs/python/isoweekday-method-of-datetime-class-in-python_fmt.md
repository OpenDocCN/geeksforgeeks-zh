# Python 中日期时间类的 isoweekday() 方法

> 原文：[https://www.geeksforgeeks.org/isoweekday-method-of-datetime-class-in-python/](https://www.geeksforgeeks.org/isoweekday-method-of-datetime-class-in-python/)

`isoweekday()` 是 `datetime` 类的一个方法，它返回给定日期对应的一周中的某一天（整数）。

> **语法：** `datetime.isoweekday()`
>
> **参数：** 无
>
> **返回值：** 根据下表返回一个对应于一周中某一天的整数。

| 返回的整数 | 一周中的某一天 |
| :--- | :--- |
| 1 | 星期一 |
| 2 | 星期二 |
| 3 | 星期三 |
| 4 | 星期四 |
| 5 | 星期五 |
| 6 | 星期六 |
| 7 | 星期日 |

## 例 1：打印当前日期的当天

```python
# importing the datetime module
import datetime

# Creating an dictionary with the return
# value as keys and the day as the value
# This is used to retrieve the day of the
# week using the return value of the
# isoweekday() function
weekdays = {1: "Monday",
            2: "Tuesday",
            3: "Wednesday",
            4: "Thursday",
            5: "Friday",
            6: "Saturday",
            7: "Sunday"}

# Getting current date using today()
# function of the datetime class
todays_date = datetime.date.today()
print("Today's date is :", todays_date)

# Using the isoweekday() function to
# retrieve the day of the given date
day = todays_date.isoweekday()
print("The date", todays_date, "falls on",
      weekdays[day])
```

**输出：**

```python
Today's date is : 2021-07-27
The date 2021-07-27 falls on Tuesday
```

## 例 2：获取 2010 年至今的今天的星期几

```python
# importing the datetime module
import datetime

# Creating an dictionary with the return
# value as keys and the day as the value
# This is used to retrieve the day of the
# week using the return value of the
# isoweekday() function
weekdays = {1: "Monday",
            2: "Tuesday",
            3: "Wednesday",
            4: "Thursday",
            5: "Friday",
            6: "Saturday",
            7: "Sunday"}

# Getting current year using today() function
# of the datetime class and the year attribute
Today = datetime.date.today()
current_year = Today.year

for i in range(2010, current_year+1):
    # Printing the day of the year
    # by first creating an datetime object
    # for the starting day of the year and
    # then we use isoweekday
    # to get the value and we use the
    # weekdays to retrieve the day of the year
    print("The {}/{} in the year {} has fallen on {}".\
          format(Today.month, Today.day, i,
          weekdays[datetime.date(i, Today.month,
                    Today.day).isoweekday()]))
```

**输出：**

> 2010 年的 7/28 已经在周三落下帷幕
>
> 2011 年的 7/28 已经在周四落下
>
> 2012 年的 7/28 发生在周六
>
> 2013 年的 7/28 发生在周日
>
> 2014 年的 7/28 已经在周一落下帷幕
>
> 2015 年的 7/28 已经在周二落下
>
> 2016 年的 7/28 已经在周四落下
>
> 2017 年的 7/28 已经在周五落下
>
> 2018 年的 7/28 已经在周六落下帷幕
>
> 2019 年的 7/28 发生在周日
>
> 2020 年的 7/28 已经在周二落下
>
> 2021 年的 7/28 已经在周三落下帷幕