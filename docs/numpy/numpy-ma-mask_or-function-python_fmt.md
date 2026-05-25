# numpy.ma.mask_or() 函数 | Python

> 原文: [https://www.geeksforgeeks.org/numpy-ma-mask_or-function-python/](https://www.geeksforgeeks.org/numpy-ma-mask_or-function-python/)

`numpy.ma.mask_or()` 函数将两个掩码与逻辑 `or` 运算符组合在一起。结果可能是 `m1` 或 `m2` 上的视图，如果另一个是 `nomask` (即 `False`)。

## 语法
`numpy.ma.mask_or(m1, m2, copy=False, shrink=True)`

## 参数
- `m1`, `m2`: 【array_like】输入遮罩。
- `copy`: 【bool, 可选】如果 `copy` 为 `False` 且其中一个输入为 `nomask`，则返回另一个输入掩码的视图。默认为 `False`。
- `shrink`: 【bool, 可选】如果输出的所有值都为 `False`，是否将输出收缩为 `nomask`。默认为 `True`。

## 返回值
结果屏蔽 `m1` 或 `m2` 中屏蔽的值。

## 代码示例 #1
```py
# Python program explaining
# numpy.ma.mask_or() function

# importing numpy as geek   
# and numpy.ma module as ma 
import numpy as geek 
import numpy.ma as ma

m1 = geek.ma.make_mask([1, 1, 0, 1])
m2 = geek.ma.make_mask([1, 0, 0, 0])

gfg = geek.ma.mask_or(m1, m2)

print (gfg)
```

**输出:**
```py
[ True  True False  True]
```

## 代码示例 #2
```py
# Python program explaining
# numpy.ma.mask_or() function

# importing numpy as geek   
# and numpy.ma module as ma 
import numpy as geek 
import numpy.ma as ma

m1 = geek.ma.make_mask([1, 0, 0, 0])
m2 = geek.ma.make_mask([1, 1, 0, 1])

gfg = geek.ma.mask_or(m1, m2)

print (gfg)
```

**输出:**
```py
[ True  True False  True]
```