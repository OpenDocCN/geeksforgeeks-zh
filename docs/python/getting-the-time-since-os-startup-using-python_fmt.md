# 使用 Python 获取操作系统启动后的时间

> 原文：[https://www.geeksforgeeks.org/getting-the-time-since-os-startup-using-python/](https://www.geeksforgeeks.org/getting-the-time-since-os-startup-using-python/)

**正常运行时间**是操作系统启动后经过的时间。操作系统有独立的机制来跟踪这个时间，它们进一步利用这个时间来执行与操作系统相关的任务。此时间对于某些应用程序尤其有用，例如：

- Usage tracking application
- Backup application
- Antivirus application

在本文中，我们将看一下从不同操作系统的操作系统启动以来获取时间的方法。

## 在 MAC 操作系统和 Linux 上获得正常运行时间

对于 Mac OS 和 Linux 用户来说，方法非常琐碎。操作系统终端提供了一个内置命令，允许提取正常运行时间。我们将把这个命令行方法集成到我们的 Python 程序中。

### 蟒 3

```py
# for using os.popen()
import os

# sending the uptime command as an argument to popen()
# and saving the returned result (after truncating the trailing \n)
t = os.popen('uptime -p').read()[:-1]

print(t)
```

**输出**

```py
 Up 6 minutes
```

**使用上述代码时需要考虑的事项：**

- 用户不需要使用 `os.popen()`。只需要调用命令行解释器，因此任何其他导致相同结果的方法/函数（`subprocess` 等）都可以替代它。
- 正常运行时间命令后的 `-p` 是为了美化输出，否则输出会包含太多不需要的信息。

## 在 WINDOWS 操作系统上获得正常运行时间

对于视窗系统，我们将使用一个内置的应用编程接口函数，该函数在视窗操作系统中以 `GetTickCount64()` 的名称出现。该函数检索系统启动后经过的毫秒数。

### 蟒 3

```py
# ctypes required for using GetTickCount64()
import ctypes

# getting the library in which GetTickCount64() resides
lib = ctypes.windll.kernel32

# calling the function and storing the return value
t = lib.GetTickCount64()

# since the time is in milliseconds i.e. 1000 * seconds
# therefore truncating the value
t = int(str(t)[:-3])

# extracting hours, minutes, seconds & days from t
# variable (which stores total time in seconds)
mins, sec = divmod(t, 60)
hour, mins = divmod(mins, 60)
days, hour = divmod(hour, 24)

# formatting the time in readable form
# (format = x days, HH:MM:SS)
print(f"{days} days, {hour:02}:{mins:02}:{sec:02}")
```

**输出**

```py
0 days, 3:09:04
```

上述输出表明，该系统正在运行 3 小时 9 分 4 秒（0 天）。如果系统使用时间超过一天（或小时数= 24+），则小时数将回滚到 0，天数将递增。

**运行上述代码时需要考虑的事项：**

- 如果您的操作系统启用了混合睡眠作为关机机制，`GetTickCount64()` 将无法正常工作。
- 此程序仅适用于 python 版本 >= 3.x，因为它包含 `f-strings`。要在 python 2 上使用此功能，请将 f 字符串更改为 `str.format()` 或 `% format`。
- `GetTickCount64()` 不包括休眠或睡眠期间经过的时间。