# numpy.nanstd()函数–Python

> 原文: `https://www.geeksforgeeks.org/numpy-nanstd-function-python/`

`numpy.nanstd()` 函数计算沿指定轴的标准偏差，而忽略 NaNs。

## 语法
`numpy.nanstd(arr, axis=None, dtype=None, out=None, ddof=0, keepdims)`

## 参数
- `arr`: 【array_like】计算非 NaN 值的标准差。
- `axis`: 【{int, int 的 tuple, None}, 可选】计算标准差的轴。
- `dtype`: 【dtype, 可选】用于计算标准差的类型。对于整数类型的数组，默认值是 `float64`，对于浮点类型的数组，它与数组类型相同。
- `out`: 【ndarray, 可选】放置结果的备选输出数组。
- `ddof`: 【int, 可选】`ddof` 表示δ自由度。计算中使用的除数是 `N - ddof`，其中 `N` 代表非 NaN 元素的数量。默认情况下，`ddof` 为零。
- `keepdims`: 【bool, 可选】如果设置为真，则缩小的轴作为尺寸为 1 的维度留在结果中。使用此选项，结果将根据原始 `arr` 正确广播。

## 返回值
【standard deviation】如果 `out` 为 `None`，则返回包含标准差的新数组，否则返回对输出数组的引用。

## 示例

**代码#1 :**

```py
# Python program explaining
# numpy.nanstd() function

# importing numpy as geek 
import numpy as geek

arr = geek.array([[1, 2], [geek.nan, 4]])

gfg = geek.nanstd(arr)

print (gfg)
```

**输出:**

```py
1.247219128924647
```

**代码#2 :**

```py
# Python program explaining
# numpy.nanstd() function

# importing numpy as geek 
import numpy as geek

arr = geek.array([[1, 2], [geek.nan, 4]])

gfg = geek.nanstd(arr, axis = 0)

print (gfg)
```

**输出:**

```py
[0. 1.]
```