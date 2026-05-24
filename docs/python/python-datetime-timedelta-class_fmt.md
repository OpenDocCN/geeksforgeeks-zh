# Python 日期时间 – timedelta 类

> 原文: [https://www.geeksforgeeks.org/python-datetime-timedelta-class/](https://www.geeksforgeeks.org/python-datetime-timedelta-class/)

`timedelta` 类用于计算日期之间的差异，代表一个持续时间。这种差异既可以是积极的，也可以是消极的。

**语法:**

> `class datetime.timedelta(days=0, seconds=0, microseconds=0, milliseconds=0, minutes=0, hours=0, weeks=0)`

## 示例

### Python 3

```py
# Timedelta function demonstration

from datetime import datetime, timedelta

# creating datetime objects
date1 = datetime(2020, 1, 3)
date2 = datetime(2020, 2, 3)

# difference between dates
diff = date2 - date1
print("Difference in dates:", diff)

# Adding days to date1
date1 += timedelta(days = 4)
print("Date1 after 4 days:", date1)

# Sutracting days from date1
date1 -= timedelta(15)
print("Date1 before 15 days:", date1)
```

**Output**

```py
Difference in dates: 31 days, 0:00:00
Date1 after 4 days: 2020-01-07 00:00:00
Date1 before 15 days: 2019-12-23 00:00:00
```

## 类属性

让我们看看这个类提供的属性：

| 属性名 | 描述 |
| --- | --- |
| `min` | `timedelta` 对象的最小值是 -999999999 天 |
| `max` | `timedelta` 对象的最大值是 999999999 天 |
| `resolution` | `timedelta` 对象之间的最小可能差异 |

### 示例：获取 timedelta 对象的最小值和最大值

### Python 3

```py
from datetime import timedelta

# Getting minimum value
Min = timedelta.min
print("Minimum value of timedelta object", Min)

# Getting minimum value
Max = timedelta.max
print("Maximum value of timedelta object", Max)
```

**Output**

```py
Minimum value of timedelta object -999999999 days, 0:00:00
Maximum value of timedelta object 999999999 days, 23:59:59.999999
```

## 类函数

`timedelta` 类只提供一个函数 `total_seconds()`。该方法返回 `timedelta` 对象提供的持续时间，以秒为单位。

**注:** 持续时间超过 270 年时，该方法精确到微秒。

### 示例：以秒为单位获取各种持续时间

### Python 3

```py
from datetime import timedelta

# Getting minimum value
obj = timedelta(hours=1)
print(obj.total_seconds())

obj = timedelta(minutes=1)
print(obj.total_seconds())

obj = timedelta(days=1)
print(obj.total_seconds())
```

**Output**

```py
3600.0
60.0
86400.0
```

## timedelta 类支持的操作

| 操作符 | 描述 |
| --- | --- |
| `+` (加法) | 添加并返回两个 `timedelta` 对象 |
| `-` (减法) | 减去并返回两个 `timedelta` 对象 |
| `*` (乘法) | 将 `timedelta` 对象乘以浮点数或整数 |
| `/` (除法) | 用浮点数或整数除 `timedelta` 对象 |
| `//` (地板除) | 用浮点数或整数除 `timedelta` 对象，并返回输出的整数值 |
| `%` (取模) | 将两个 `timedelta` 对象相除，并返回余数 |
| `+` (一元加) | 返回相同的 `timedelta` 对象 |
| `-` (一元减) | 返回 `-1 * timedelta` 的结果 |
| `abs()` | 如果 `timedelta.days >= 0`，则返回 `+timedelta`，否则返回 `-timedelta` |
| `str()` | 返回一个格式为 `(+/-)D days, HH:MM:SS.ffffff` 的字符串 |
| `repr()` | 返回构造函数调用形式的字符串表示形式 |

### 示例 1：对 timedelta 对象执行基本算术运算

### Python 3

```py
from datetime import timedelta

# creating the timedelta object
t1 = timedelta(days=1)
print("Original timedelta:", t1)

# multiplication
t2 = t1*5.5
print("After Multiplication:", t2)

# Subtraction
res = t2 - t1
print("After Subtraction:", res)

# addition
res += t2
print("After Addition:", res)

# division
res = t2/2.5
print("After division:", res)

# floor division
res = t2 //2
print("After floor division:", res)

# Modulo
res = t2%timedelta(days=3)
print("After Modulo:", res)
```

**Output**

```py
Original timedelta: 1 day, 0:00:00
After Multiplication: 5 days, 12:00:00
After Subtraction: 4 days, 12:00:00
After Addition: 10 days, 0:00:00
After division: 2 days, 4:48:00
After floor division: 2 days, 18:00:00
After Modulo: 2 days, 12:00:00
```

### 示例 2：获取 timedelta 对象的绝对值和字符串表示

### Python 3

```py
from datetime import timedelta

# creating the timedelta object
t1 = timedelta(days=1)
print("Original timedelta:", t1)

# Negation of timedelta object
t1 = -(t1)
print("After Negation:", t1)

# Getting Absolute value
t1 = abs(t1)
print("Absolute Value:", t1)

# Getting string representation
print("String representation:", str(t1))

# Getting Constructor call
print("Constructor call:", repr(t1))
```

**Output**

```py
Original timedelta: 1 day, 0:00:00
After Negation: -1 day, 0:00:00
Absolute Value: 1 day, 0:00:00
String representation: 1 day, 0:00:00
Constructor call: datetime.timedelta(1)
```

**注:** 关于 Python Datetime 的更多信息，请参考 [Python Datetime 教程](https://www.geeksforgeeks.org/python-datetime-module/)。