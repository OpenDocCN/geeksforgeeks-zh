# Python 日期时间–时间类

> 原文：[https://www.geeksforgeeks.org/python-datetime-time-class/](https://www.geeksforgeeks.org/python-datetime-time-class/)

`Time` 类表示一天中独立于任何特定日期的本地时间。这个类可以有 `tzinfo` 对象，表示给定时间的时区。如果 `tzinfo` 为 `None`，则时间对象是“天真的”对象，否则它是“感知的”对象。

**语法：**

> `class datetime.time(hour=0, minute=0, second=0, microsecond=0, tzinfo=None, *, fold=0)`

所有参数都是可选的。`tzinfo` 可以是 `None`，否则所有属性必须是以下范围内的整数：

*   `0 <= hour < 24`
*   `0 <= minute < 60`
*   `0 <= second < 60`
*   `0 <= microsecond < 1000000`
*   `fold` `[0, 1]`

**示例：**

## Python 3

```py
# Python program to
# demonstrate time class

from datetime import time

# calling the constructor
my_time = time(12, 14, 36)

print("Entered time", my_time)

# calling constructor with 1
# argument
my_time = time(minute = 12)
print("\nTime with one argument", my_time)

# Calling constructor with
# 0 argument
my_time = time()
print("\nTime without argument", my_time)

# Uncommenting time(hour = 26)
# will rase an ValueError as
# it is out of range

# uncommenting time(hour ='23')
# will raise TypeError as
# string is passed instead of int
```

**Output**

```py
Entered time 12:14:36

Time with one argument 00:12:00

Time without argument 00:00:00
```

## 类别属性

让我们看看这个类提供的属性：

| 属性名 | 描述 |
| --- | --- |
| `min` | 时间的最小可能表示 |
| `max` | 时间的最大可能表示 |
| `resolution` | 时间对象之间的最小可能差异 |
| `hour` | 小时范围必须介于 0 和 24 之间（不包括 24） |
| `minute` | 分钟范围必须介于 0 和 60 之间（不包括 60） |
| `second` | 秒的范围必须介于 0 和 60 之间（不包括 60） |
| `microsecond` | 微秒范围必须介于 0 和 1000000 之间（不包括 1000000） |
| `tzinfo` | 包含时区信息的对象 |
| `fold` | 表示折叠是否发生在 |

**示例 1：** 获取最小和最大可表示时间

## Python 3

```py
from datetime import time

# Getting min time
mintime = time.min
print("Min Time supported", mintime)

# Getting max time
maxtime = time.max
print("Max Time supported", maxtime)
```

**Output**

```py
Min Time supported 00:00:00
Max Time supported 23:59:59.999999
```

**示例 2：** 从时间类访问小时、分钟、秒和微秒属性

## Python 3

```py
from datetime import time

# Creating Time object
Time = time(12,24,36,1212)

# Accessing Attributes
print("Hour:", Time.hour)
print("Minutes:", Time.minute)
print("Seconds:", Time.second)
print("Microseconds:", Time.microsecond)
```

**Output**

```py
Hour: 12
Minutes: 24
Seconds: 36
Microseconds: 1212
```