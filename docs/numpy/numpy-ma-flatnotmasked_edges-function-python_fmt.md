# numpy.ma.flatnotmasked_edges() 函数 | Python

> 原文: [https://www.geeksforgeeks.org/numpy-ma-flatnotmasked_edges-function-python/](https://www.geeksforgeeks.org/numpy-ma-flatnotmasked_edges-function-python/)

`numpy.ma.flatnotmasked_edges()` 函数查找第一个和最后一个未屏蔽值的索引。

## 语法
`numpy.ma.flatnotmasked_edges(arr)`

## 参数
- **arr**: 【array_like】 输入一维 MaskedArray。

## 返回值
【ndarray 或 None】 数组中第一个和最后一个非掩码值的索引。如果所有值都被屏蔽，则返回 `None`。

## 代码示例 1

```py
# Python program explaining
# numpy.ma.flatnotmasked_edges() function

# importing numpy as geek   
# and numpy.ma module as ma 
import numpy as geek 
import numpy.ma as ma

arr = geek.ma.arange(12)

gfg = geek.ma.flatnotmasked_edges(arr)

print (gfg)
```

**输出:**

```py
[ 0, 11]
```

## 代码示例 2

```py
# Python program explaining
# numpy.ma.flatnotmasked_edges() function

# importing numpy as geek   
# and numpy.ma module as ma 
import numpy as geek 
import numpy.ma as ma

arr = geek.ma.arange(12)
arr[:] = geek.ma.masked

gfg = geek.ma.flatnotmasked_edges(arr)

print (gfg)
```

**输出:**

```py
None
```