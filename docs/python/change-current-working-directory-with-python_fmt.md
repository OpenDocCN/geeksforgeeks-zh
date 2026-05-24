# 用 Python 改变当前工作目录

> 原文: [https://www.geeksforgeeks.org/change-current-working-directory-with-python/](https://www.geeksforgeeks.org/change-current-working-directory-with-python/)

`os`模块用于与操作系统交互。该模块属于 Python 的标准实用程序模块，因此无需从外部安装。`os`模块中的所有函数在文件名和路径无效或不可访问的情况下，或者在具有正确类型但不被操作系统接受的其他参数的情况下，都会引发`OSError`。

改变当前工作目录（CWD）使用`os.chdir()`方法。此方法将 CWD 更改为指定路径。它只接受一个参数作为新的目录路径。

**注意:** 当前工作目录是 Python 脚本运行的文件夹。

> **语法:** `os.chdir(path)`
> **参数:**
> `path`: 要更改到新目录路径的目录的完整路径。
> **返回:** 不返回任何值

### 示例#1

我们首先获取脚本的当前工作目录，然后进行修改。下面是实现。

```py
# Python program to change the
# current working directory

import os

# Function to Get the current
# working directory
def current_path():
    print("Current working directory before")
    print(os.getcwd())
    print()

# Driver's code
# Printing CWD before
current_path()

# Changing the CWD
os.chdir('../')

# Printing CWD after
current_path()
```

**输出:**

```py
Current working directory before
C:\Users\Nikhil Aggarwal\Desktop\gfg

Current working directory after
C:\Users\Nikhil Aggarwal\Desktop
```

### 示例#2

更改目录时处理错误。

```py
# Python program to change the
# current working directory

# importing all necessary libraries
import sys, os

# initial directory
cwd = os.getcwd()

# some non existing directory
fd = 'false_dir/temp'

# trying to insert to false directory
try:
    print("Inserting inside-", os.getcwd())
    os.chdir(fd)

# Caching the exception     
except:
    print("Something wrong with specified directory. Exception- ")
    print(sys.exc_info())

# handling with finally           
finally:
    print()
    print("Restoring the path")
    os.chdir(cwd)
    print("Current directory is-", os.getcwd())
```

**输出:**

> 插入内部- C:\Users\Nikhil Aggarwal\Desktop\gfg
> 指定目录有问题。异常-
> (<class 'FileNotFoundError'>, FileNotFoundError(2, '系统找不到指定路径'), <traceback object at 0x00000268184630C8>)
> 恢复路径
> 当前目录为- C:\Users\Nikhil Aggarwal\Desktop\gfg