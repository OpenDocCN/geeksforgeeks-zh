# 来自 Python 中 `datetime.date` 类的 `fromisoformat()` 函数

> 原文: [https://www.geeksforgeeks.org/fromisoformat-function-of-datetime-date-class-in-python/](https://www.geeksforgeeks.org/fromisoformat-function-of-datetime-date-class-in-python/)

`fromisoformat()` 函数用于根据包含 ISO 格式日期的指定字符串构造日期对象。即 `yyyy-mm-dd`。

> **语法:** `@classmethod fromisoformat(date_string)`
>
> **参数:** 该函数接受如下所示的参数:
>
> *   `date_string`: 这是指定的 ISO 格式，即 `yyyy-mm-dd` 日期字符串，其日期对象将被构造。
>
> **返回值:** 该函数返回由指定的 ISO 格式日期字符串构造的日期对象。

## 示例 1

从包含 ISO 格式日期的指定字符串中获取日期对象。即 `yyyy-mm-dd`。

### Python 3

```py
# Python3.7 code for Getting
# a date object from a specified
# string that contains date in
# ISO format. i.e., yyyy-mm-dd

# Importing datetime module
import datetime

# Initializing a date
Date = "2012-10-12";

# Calling fromisoformat() function to
# construct a datetime.date object
New_date = datetime.date.fromisoformat(Date);

# Printing the new constructed date object
print("The constructed date object is: %s"%New_date);
```

**输出:**

```py
The constructed date object is: 2012-10-12
```

## 示例 2

获取指定日期新创建的日期对象。

### Python 3

```py
# Python3.7 code for Getting
# a date object from a specified
# string that contains date in
# ISO format. i.e., yyyy-mm-dd

# Importing datetime module
from datetime import date

# Calling the fromisoformat() function
# to Print the new created date object
# for the specified date in
# ISO format of 2020-10-09
print(date.fromisoformat('2020-10-09'))
```

**输出:**

```py
2020-10-09
```