# 如何修复：名称错误名称‘np’未定义

> 原文：[https://www.geeksforgeeks.org/how-to-fix-nameerror-name-np-is-not-defined/](https://www.geeksforgeeks.org/how-to-fix-nameerror-name-np-is-not-defined/)

在本文中，我们将讨论如何修复 Python 中没有定义的名称错误 `np`。

当我们导入不带别名的 `numpy` 模块并在代码中使用 `np` 时，会出现错误。

`示例`：描述错误的代码

## Python 3

```py
# import numpy module
import numpy

# create numpy array
a = np.array([1, 2, 3, 45])

# display
a
```

`输出`：

```py
name 'np' is not defined
```

这里 `np` 是 `numpy` 模块的别名，所以我们可以导入有别名的 `numpy` 模块，也可以导入没有别名的 `numpy` 模块并直接使用该名称。

## 方法 1：通过在导入 numpy 时使用别名

我们可以在导入时使用别名来解决错误。

`语法`：

```py
import numpy as np
```

`示例`：导入 `numpy` 作为别名的程序

### Python 3

```py
# import numpy module
import numpy as np

# create numpy array
a = np.array([1, 2, 3, 45])

# display
a
```

`输出`：

```py
array([ 1,  2,  3, 45])
```

## 方法 2：直接使用 NumPy

我们可以直接使用 `numpy` 模块在一个数据结构中使用。

`语法`：

```py
import numpy
```

`示例`：直接使用 `numpy`

### Python 3

```py
# import numpy module
import numpy

# create numpy array
a = numpy.array([1, 2, 3, 45])

# display
a
```

`输出`：

```py
array([ 1,  2,  3, 45])
```