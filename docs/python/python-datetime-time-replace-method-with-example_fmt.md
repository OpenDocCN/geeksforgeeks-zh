# Python datetime.time.replace()方法详解

> 原文：[https://www.geeksforgeeks.org/python-datetime-time-replace-method-with-example/](https://www.geeksforgeeks.org/python-datetime-time-replace-method-with-example/)

在本文中，我们将讨论 Python 中的 `time.replace()` 方法。此方法用于操作 `datetime` 模块的 `time` 类对象。它用于创建一个新的时间对象，其值与原对象相同，但由任何关键字参数指定的字段被赋予新值。

> **语法：** `replace(hour=self.hour, minute=self.minute, second=self.second, microsecond=self.microsecond, tzinfo=self.tzinfo, *, fold=0)`
>
> **参数：**
>
> *   `hour`：新小时值（范围：`0 <= hour < 24`）
> *   `minute`：新分钟值（范围：`0 <= minute < 60`）
> *   `second`：新秒值（范围：`0 <= second < 60`）
> *   `microsecond`：新微秒值（范围：`0 <= microsecond < 1000000`）
> *   `tzinfo`：新的 `tzinfo` 对象。
> *   `fold`：在 `0` 或 `1` 之间。
>
> **返回：** 一个新的 `time` 对象。

**Python 程序获取时间并显示：**

## 示例

```python
# import time from datetime
from datetime import time

# create time
x = time(5,34,7,6789)
print("Time:", x)
```

**输出：**

```
Time: 05:34:07.006789
```

### 示例 1：替换给定时间的小时

```python
# import time from datetime
from datetime import time

# create time
x = time(5, 34, 7, 6789)

print("Actual Time:", x)

# replace hour from 5 to 10
final = x.replace(hour = 10)

print("New time after changing the hour:", final)
```

**输出：**

```
Actual Time: 05:34:07.006789
New time after changing the hour: 10:34:07.006789
```

### 示例 2：替换给定时间的分钟

```python
# import time from datetime
from datetime import time

# create time
x = time(5, 34, 7, 6789)

print("Actual Time:", x)

# replace minute from 34 to 12
final = x.replace(minute = 12)

print("New time after changing the minute:", final)
```

**输出：**

```
Actual Time: 05:34:07.006789
New time after changing the minute: 05:12:07.006789
```

### 示例 3：替换给定时间的秒

```python
# import time from datetime
from datetime import time

# create time
x = time(5,34,7,6789)

print("Actual Time:", x)

# replace second from 7 to 2
final = x.replace(second = 2)

print("New time after changing the second:", final)
```

**输出：**

```
Actual Time: 05:34:07.006789
New time after changing the second: 05:34:02.006789
```

### 示例 4：同时替换多个字段

```python
# import time from datetime
from datetime import time

# create time
x = time(5,34,7,6789)

print("Actual Time:", x)

# replace hour from 5 to 10
# replace minute from 34 to 11
# replace second from 7 to 1
# replace microsecond from 6789 to 1234
final = x.replace(hour = 10, minute = 11,
                  second = 1, microsecond = 1234)

print("New time :", final)
```

**输出：**

```
Actual Time: 05:34:07.006789
New time : 10:11:01.001234
```