# numpy.dtype.subdtype()函数–Python

> 原文: [https://www.geeksforgeeks.org/numpy-dtype-subdtype-function-python/](https://www.geeksforgeeks.org/numpy-dtype-subdtype-function-python/)

`numpy.dtype.subdtype()` 函数返回 Tuple(item_dtype，shape)，如果这个 dtype 描述了一个子数组，否则返回 None。

## 语法
`numpy.dtype.subdtype(类型)`

**类型:** 【数据类型】输入数据类型。
**返回:** 如果元组(item_dtype，shape)描述子数组，则返回元组(item_dtype，shape)，否则返回无。

**代码#1 :**

```py
# Python program explaining
# numpy.dtype.subdtype() function

# importing numpy as geek 
import numpy as geek

x = geek.dtype('8f')

gfg = x.subdtype

print (gfg)
```

**输出:**

```py
(dtype('float32'), (8, ))
```

**代码#2 :**

```py
# Python program explaining
# numpy.dtype.subdtype() function

# importing numpy as geek 
import numpy as geek

x = geek.dtype('i2')

gfg = x.subdtype

print (gfg)
```

**输出:**

```py
None
```