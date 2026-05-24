# 使用 Python shutil.rmtree() 方法删除整个目录树

> 原文: [https://www.geeksforgeeks.org/delete-an-entire-directory-tree-using-python-shutil-rmtree-method/](https://www.geeksforgeeks.org/delete-an-entire-directory-tree-using-python-shutil-rmtree-method/)

`shutil` 模块提供了很多对文件和文件集合进行高级操作的功能。它属于 Python 的标准实用程序模块。该模块有助于自动化文件和目录的复制和删除过程。
`shutil.rmtree()` 用于删除整个目录树，路径必须指向一个目录（但不是指向一个目录的符号链接）。

> **语法:** `shutil.rmtree(path, ignore_errors=False, onerror=None)`
> **参数:**
> `path`: 表示文件路径的类路径对象。类似路径的对象是表示路径的字符串或字节对象。
> `ignore_errors`: 如果 `ignore_errors` 为真，则删除失败导致的错误将被忽略。
> `onerror`: 如果 `ignore_errors` 为 false 或省略，则通过调用 `onerror` 指定的处理程序来处理此类错误。

**例 1:** 假设目录和子目录如下。
**#父目录:**

![python shutil.rmtree()](img/3136a3b16bc368d766d2f1ad52f9e2c0.png)

**#父目录内目录:**

![python shutil.rmtree()](img/6a8ee7c2e99ed708e5685a8be970c7eb.png)

**#文件内子目录:**

![python shutil.rmtree()](img/f43a4dddb9fa147575b0cbfbace9aa04.png)

我们想删除目录 `Authors`。下面是实现。

## 蟒蛇 3

```py
# Python program to demonstrate
# shutil.rmtree()

import shutil
import os

# location
location = "D:/Pycharm projects/GeeksforGeeks/"

# directory
dir = "Authors"

# path
path = os.path.join(location, dir)

# removing directory
shutil.rmtree(path)
```

**输出:**

![python shutil.rmtree()](img/3266bfd4fa4db10ee09fd759eccf0f12.png)

**示例 2:** 通过传递 `ignore_errors = False`。

## 蟒蛇 3

```py
# Python program to demonstrate
# shutil.rmtree()

import shutil
import os

# location
location = "D:/Pycharm projects/GeeksforGeeks/"

# directory
dir = "Authors"

# path
path = os.path.join(location, dir)

# removing directory
shutil.rmtree(path, ignore_errors = False)

# making ignore_errors = True will not raise
# a FileNotFoundError
```

**输出:**

> 回溯（最近一次调用最后一次）:
> 文件 “D:/Pycharm project/gfg/gfg.py”，第 16 行，在
> `shutil.rmtree(path, ignore_errors=False)`
> 文件 “C:\Users\Nikhil Aggarwal\AppData\Local\Programs\Python\Python38-32\lib\shutil.py”，第 730 行，在 `rmtree`
> return `_rmtree_unsafe(path, onerror)`
> 文件 “C:\Users\Nikhil

**例 3:** 通过传递一个 `onerror`。
在 `onerror` 中，应该传递一个必须包含三个参数的函数。

*   **函数:** 引发异常的函数。
*   **路径:** 在移除时引发异常的路径名。
*   **exc_info:** `sys.exc_info()` 引发异常信息。

下面是实现。

## 蟒蛇 3

```py
# Python program to demonstrate
# shutil.rmtree()

import shutil
import os

# exception handler
def handler(func, path, exc_info):
    print("Inside handler")
    print(exc_info)

# location
location = "D:/Pycharm projects/GeeksforGeeks/"

# directory
dir = "Authors"

# path
path = os.path.join(location, dir)

# removing directory
shutil.rmtree(path, onerror = handler)
```

**输出:**

> Inside handler
> (<class 'FileNotFoundError'>, FileNotFoundError(2, '系统找不到指定的路径'), <traceback object at 0x000002...>)
> Inside handler
> (<class 'FileNotFoundError'>, FileNotFoundError(2, '系统找不到指定的文件'), <traceback object at 0x000002...>)