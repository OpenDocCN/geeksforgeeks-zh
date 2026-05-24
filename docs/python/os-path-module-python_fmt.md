# Python 中的操作系统路径模块

> 原文：[https://www.geeksforgeeks.org/os-path-module-python/](https://www.geeksforgeeks.org/os-path-module-python/)

这个模块包含一些关于路径名的有用函数。路径参数为字符串或字节。这里的这些函数用于不同的目的，例如在 Python 中合并、规范化和检索路径名。所有这些函数都只接受字节或字符串对象作为参数。如果返回路径或文件名，则结果是相同类型的对象。因为有不同版本的操作系统，所以在标准库中有几个版本的这个模块。

以下是操作系统路径模块的一些功能。

## `os.path.basename()` 函数
用于返回文件的 basename。这个函数基本上从给定的路径返回文件名。

```py
# basename function
import os
out = os.path.basename("/baz/foo")
print(out)
```

输出：

```py
'foo'
```

## `os.path.dirname()` 函数
用于从给定路径返回目录名。此函数从路径中返回除路径名以外的名称。

```py
# dirname function
import os
out = os.path.dirname("/baz/foo")
print(out)
```

输出：

```py
'/baz'
```

## `os.path.isabs()` 函数
指定路径是否为绝对路径。在 Unix 系统中，绝对路径是指路径以斜杠（`/`）开头，在 Windows 系统中，它是在切掉一个潜在的驱动器号后以一个（后）斜杠开头。

```py
# isabs function
import os
out = os.path.isabs("/baz/foo")
print(out)
```

输出：

```py
True
```

## `os.path.isdir()` 函数
该函数指定路径是否为现有目录。

```py
# isdir function
import os
out = os.path.isdir("C:\\Users")
print(out)
```

输出：

```py
True
```

## `os.path.isfile()` 函数
此函数指定路径是否为现有文件。

```py
# isfile function
import os
out = os.path.isfile("C:\\Users\foo.csv")
print(out)
```

输出：

```py
True
```

## `os.path.normcase()` 函数
此函数将指定路径名的大小写规范化。在 Unix 和 Mac OS X 系统中，它按原样返回路径名。但是在 Windows 中，它将路径转换为小写，将正斜杠转换为反斜杠。

```py
# normcase function in windows
import os
out = os.path.normcase("/BAz")
print(out)
```

输出：

```py
'\\baz'
```

## `os.path.normpath()` 函数
此函数通过折叠冗余分隔符和上层引用来规范化路径名，以便 `A//B`，`A/B/`，`A/./B` 和 `A/foo/../B` 全部变成 `A/B`。在 Windows 上，它将正斜杠转换为反斜杠。

```py
# normpath function in Unix
import os
out = os.path.normpath("foo/./bar")
print(out)
```

输出：

```py
'foo/bar'
```

还有很多功能，可以参考 [Python](https://docs.python.org/3/library/os.path.html) 官方文档。

**参考资料：**
[Python 文档](https://docs.python.org/3/library/os.path.html)