# Python 日历模块：`itermonthdays()`方法

原文：[https://www.geeksforgeeks.org/python-calendar-module-itermonthdays-method/](https://www.geeksforgeeks.org/python-calendar-module-itermonthdays-method/)

日历模块允许像程序一样输出日历，并提供与日历相关的附加有用功能。日历模块中定义的函数和类使用理想化的日历，当前的公历在两个方向上无限延长。

`itermonthdays()` 方法返回指定月份和年份的迭代器。返回的天数只是天数。`itermonthdays()`方法类似于 `itermonthdates()`。

```
Syntax: itermonthdays(year, month)

Parameter: 
year: year of the calendar
month: month of the calendar

Returns: an iterator of the specified month.
```

代码#1：

## Python 3

```py
# Python program to demonstrate working
# of itermonthdays() method

# importing calendar module
import calendar

year = 2018
month = 9

obj = calendar.Calendar()

# iterating with itermonthdays
for day in obj.itermonthdays(year, month):
    print(day)
```

输出：

```py

.
.

```

代码#2：

## Python 3

```py
# Python program to demonstrate working
# of itermonthdays() method

# importing calendar module
import calendar

# use with firstweekday = 5
obj = calendar.Calendar(firstweekday = 2)

# iterating with itermonthdays
for day in obj.itermonthdays(2018, 4):
    print(day)
```

输出：

```py

.
.

```