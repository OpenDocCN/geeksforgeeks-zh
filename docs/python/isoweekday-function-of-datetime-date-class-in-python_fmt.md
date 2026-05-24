# Python 中 `datetime.date` 类的 `isoweekday()` 函数

> 原文：[https://www.geeksforgeeks.org/isoweekday-function-of-datetime-date-class-in-python/](https://www.geeksforgeeks.org/isoweekday-function-of-datetime-date-class-in-python/)

`isoweekday()` 是一个返回整数的函数，该整数表示给定的日期是一周中的哪一天。根据下表，它返回的整数代表一天。

> **语法：** `datetime.isoweekday()`
> **返回值：** 范围为 `[1, 7]` 的整数

| 返回的整数 | 一周中的某一天 |
| :--- | :--- |
| 1 | 星期一 |
| 2 | 星期二 |
| 3 | 星期三 |
| 4 | 星期四 |
| 5 | 星期五 |
| 6 | 星期六 |
| 7 | 星期日 |

## 示例 1
这个程序使用 `datetime` 模块获取日期，并判断该日期是星期几。

### Python 3
```python
# importing the datetime module
import datetime

# Creating an list which will
# be  used to retrieve the day of the
# week using the return value of the
# isoweekday() function
DaysList = ["None",
            "Monday",
            "Tuesday",
            "Wednesday",
            "Thursday",
            "Friday",
            "Saturday",
            "Sunday"]

# Using the function today()
# to get today's date
CurrentDate = datetime.date.today()
print("Current Date is :", CurrentDate)

# Using the isoweekday() function to
# retrieve the day of the given date
day = CurrentDate.isoweekday()
print("The date", CurrentDate, "falls on",
      DaysList[day])
```

**输出：**
```python
Current Date is : 2021-08-18
The date 2021-08-18 falls on Wednesday
```

## 示例 2
在本例中，我们将接受用户输入的日期，并返回它是星期几。

### Python 3
```python
# importing the datetime module
import datetime

# Creating an dictionary with the return
# value as keys and the day as the value
# This is used to retrieve the day of the week
# using the return value of the isoweekday()
# function
DaysList = ["None",
            "Monday",
            "Tuesday",
            "Wednesday",
            "Thursday",
            "Friday",
            "Saturday",
            "Sunday"]

# Getting the  user's input
day = 18
month = 9
year = 2020

# Creating the datetime object for the user's
# input by using the date() function of datetime
# class
Date = datetime.date(year, month, day)

# Using the isoweekday() function
# to retrieve the day of the given date
day = Date.isoweekday()

print("The given date", Date, "falls on",
      DaysList[day])
```

**输出：**
```python
The given date 2020-09-18 falls on Friday
```

## 示例 3
在本例中，我们将获取用户输入的日期，并判断它是否是用户预期的星期几。

### Python 3
```python
# importing the datetime module
import datetime

# Creating an dictionary with the return
# value as keys and the day as the value
# This is used to retrieve the day of the week
# using the return value of the isoweekday()
# function
DaysList = ["None",
            "Monday",
            "Tuesday",
            "Wednesday",
            "Thursday",
            "Friday",
            "Saturday",
            "Sunday"]

# Getting the  user's input
day = 1
month = 1
year = 2021
day_fallen = "Friday"

# Creating the datetime object for the user's
# input by using the date() function of datetime
# class
Date = datetime.date(year, month, day)

# Using the isoweekday() function
# to retrieve the day of the given date
day = Date.isoweekday()

# Checking if the day is matching the user's
# day
if day_fallen.lower() == DaysList[day].lower():
    print("Yes, your given date", Date,
          "falls on your expected day i.e ",
          DaysList[day])
else:
    print("No, your given date", Date, "falls on",
          DaysList[day],
          "but not on", day_fallen)
```

**输出：**
```python
Yes, your given date 2021-01-01 falls on your expected day i.e  Friday
```