# Python 中的环境错误异常

> 原文: [https://www.geeksforgeeks.org/environmenterror-exception-in-python/](https://www.geeksforgeeks.org/environmenterror-exception-in-python/)

**环境错误**是来自 Python 外部（操作系统、文件系统等）的错误的基类。它是 `IOError` 和 `OSError` 例外的父类。

1.  **异常 `IOError`** – 当输入/输出操作（当文件对象的方法）失败时引发。例如“找不到文件”或“磁盘已满”。
2.  **异常 `OSError`** – 当函数返回系统相关错误时引发。

任何错误或错误的例子也应该是环境错误的例子。

### 示例 1

#### Python 3

```py
# importing the module
import sys

try:
    # an invalid path
    file = open("GeeksforGeeks.txt", 'r')
except Exception as e:
    print(e)
    print(sys.exc_info()[0])
```

**输出**

```
[Errno 2] No such file or directory: 'GeeksforGeeks.txt'
<class 'FileNotFoundError'>
```

### 示例 2

#### Python 3

```py
# importing the module
import os
import sys

try:
    for i in range(7):
        print(i)
        print(os.ttyname(i))
except Exception as e:
    print(e)
    print(sys.exc_info()[0])
```

**输出**

```
[Errno 25] Inappropriate ioctl for device
<class 'OSError'>
```

### 示例 3

#### Python 3

```py
# importing the module
import sys
import os

try:
    # an invalid path
    os.rmdir('GEEKS')
except Exception as e:
    print(e)
    print(sys.exc_info()[0])
```

**输出**

```
[Errno 2] No such file or directory: 'GEEKS'
<class 'FileNotFoundError'>
```