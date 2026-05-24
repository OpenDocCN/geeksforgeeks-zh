# Python DateTime weekday()方法示例

> 原文: [https://www.geeksforgeeks.org/python-datetime-weekday-method-with-example/](https://www.geeksforgeeks.org/python-datetime-weekday-method-with-example/)

在本文中，我们将讨论 `DateTime` 模块中的 `weekday()` 函数。`weekday()` 函数用于根据给定的 `DateTime` 获取周数。它将返回 0-6 范围内的数字。

| 表示 | 表示 |
| --- | --- |
| Zero | 星期一 |
| one | 星期二 |
| Two | 星期三 |
| three | 星期四 |
| four | 星期五 |
| five | 星期六 |
| six | 星期日 |

它将以“(YYYY, MM, DD, HH, MM, SS)”的格式将输入作为日期时间，其中：
*   YYYY 代表年
*   MM 代表月
*   DD 代表日期
*   HH 代表小时
*   MM 代表分钟
*   SS 代表第二

我们首先需要导入 `DateTime` 模块并创建一个 `DateTime`，现在使用 `weekday()` 函数我们将获得特定 `DateTime` 的 weekday。

**语法:**

> `datetime(year, month, day, hour, minute, second).weekday()`

我们还可以使用以下语法从日期时间中提取日期：

**语法:**

> `datetime(year, month, day, hour, minute, second).date()`

**示例**: 创建日期时间并显示日期时间和日期的 Python 程序

## 蟒蛇 3

```py
# importing datetime class
from datetime import datetime

# create datetime
x = datetime(2021, 8, 8, 12, 5, 6)

# display
print("Datetime is :", x)

# get the date
print("Date is :", x.date())
```

**输出:**

```
Datetime is : 2021-08-08 12:05:06
Date is : 2021-08-08
```

**示例:** 获取给定日期时间的工作日的 Python 程序

## 蟒蛇 3

```py
# importing datetime class
from datetime import datetime

# create datetime
x = datetime(2021, 8, 8, 12, 5, 6)

# display
print("Datetime is :", x)

# get the weekday
print("weekday is :", x.weekday())

# create datetime
x = datetime(2021, 9, 10, 12, 5, 6)

# display
print("Datetime is :", x)

# get the weekday
print("weekday is :", x.weekday())

# create datetime
x = datetime(2020, 1, 8, 12, 5, 6)

# display
print("Datetime is :", x)

# get the weekday
print("weekday is :", x.weekday())
```

**输出:**

```
Datetime is : 2021-08-08 12:05:06
weekday is : 6
Datetime is : 2021-09-10 12:05:06
weekday is : 4
Datetime is : 2020-01-08 12:05:06
weekday is : 2
```

**例 3:** Python 程序获取工作日名称

## 蟒蛇 3

```py
# create a list of weekdays
from datetime import datetime

days = ["Monday", "Tuesday", "Wednesday",
        "Thursday", "Friday", "Saturday", "Sunday"]

# importing datetime class

# create datetime
x = datetime(2021, 8, 8, 12, 5, 6)

# display
print("Datetime is :", x)

# get the weekday name using index
print("weekday is :", days[x.weekday()])

# create datetime
x = datetime(2021, 9, 10, 12, 5, 6)

# display
print("Datetime is :", x)

# get the weekday name  using index
print("weekday is :", days[x.weekday()])

# create datetime using index
x = datetime(2020, 1, 8, 12, 5, 6)

# display
print("Datetime is :", x)

# get the weekday name using index
print("weekday is :", days[x.weekday()])
```

**输出:**

```
Datetime is : 2021-08-08 12:05:06
weekday is : Sunday
Datetime is : 2021-09-10 12:05:06
weekday is : Friday
Datetime is : 2020-01-08 12:05:06
weekday is : Wednesday
```