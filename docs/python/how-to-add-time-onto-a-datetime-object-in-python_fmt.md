# 如何在 Python 中给日期时间对象添加时间

> 原文：[https://www.geeksforgeeks.org/how-to-add-time-onto-a-datetime-object-in-python/](https://www.geeksforgeeks.org/how-to-add-time-onto-a-datetime-object-in-python/)

在本文中，我们将讨论在 Python 中将时间添加到指定的 `DateTime` 对象中。这将产生一个新的日期时间对象。这个加法可以使用 [`datetime.timedelta()`](https://www.geeksforgeeks.org/python-datetime-timedelta-function/) 函数进行。`timedelta()` 函数用于计算日期差异，也可用于 Python 中的日期操作。这是执行日期操作最简单的方法之一。

> **语法：** `datetime.timedelta(days=0, seconds=0, microseconds=0, milliseconds=0, minutes=0, hours=0, weeks=0)`
>
> **返回值：** 该函数返回操作日期。

因此，通过简单地将适当的值传递给上述给定的参数，就可以实现所需的任务。

**示例 1：** 向日期时间对象添加时间

## Python 3

```py
# Python3 code to illustrate the addition
# of time onto the datetime object

# Importing datetime
import datetime

# Initializing a date and time
date_and_time = datetime.datetime(2021, 8, 22, 11, 2, 5)

print("Original time:")
print(date_and_time)

# Calling the timedelta() function 
time_change = datetime.timedelta(minutes=75)
new_time = date_and_time + time_change

# Printing the new datetime object
print("changed time:")
print(new_time)
```

**输出：**

```py
Original time:
2021-08-22 11:02:05
changed time:
2021-08-22 12:17:05
```

**示例 2：** 通过向日期时间添加时间来更改日期

## Python 3

```py
# Python3 code to illustrate the addition
# of time onto the datetime object

# Importing datetime
import datetime

# Initializing a date and time
date_and_time = datetime.datetime(2021, 8, 22, 11, 2, 5)

print("Original time:")
print(date_and_time)

# Calling the timedelta() function
time_change = datetime.timedelta(hours=36)
new_time = date_and_time + time_change

# Printing the new datetime object
print("changed time:")
print(new_time)
```

**输出：**

```py
Original time:
2021-08-22 11:02:05
changed time:
2021-08-23 23:02:05
```

**例 3：** 同时改变两个参数

## Python 3

```py
# Python3 code to illustrate the addition
# of time onto the datetime object

# Importing datetime
import datetime

# Initializing a date and time
date_and_time = datetime.datetime(2021, 8, 22, 11, 2, 5)

print("Original time:")
print(date_and_time)

# Calling the timedelta() function and
# adding 2 minutes and 10 seconds
time_change = datetime.timedelta(minutes=2, seconds=10)
new_time = date_and_time + time_change

# Printing the new datetime object
print("changed time:")
print(new_time)
```

**输出：**

```py
Original time:
2021-08-22 11:02:05
changed time:
2021-08-22 11:04:15
```