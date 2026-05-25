# numpy.ma.mask_rowcols() 函数

> 原文: [https://www.geeksforgeeks.org/numpy-ma-mask_rowcols-function-python/](https://www.geeksforgeeks.org/numpy-ma-mask_rowcols-function-python/)

`numpy.ma.mask_rowcols()` 函数用于屏蔽包含屏蔽值的 2D 数组的行和/或列。使用 `axis` 参数选择遮罩行为。
- 如果 `axis` 为 `None`，则行和列被屏蔽。
- 如果 `axis` 为 `0`，则仅屏蔽行。
- 如果 `axis` 为 `1` 或 `-1`，则仅屏蔽列。

## 语法
`numpy.ma.mask_rowcols(arr, axis=None)`

## 参数
- `arr`: 【array_like, MaskedArray】该数组为 mask。结果是掩码设置为 `nomask` (`False`) 的掩码数组。必须是 2D 阵。
- `axis`: 【int, 可选】执行操作的轴。默认值为 `None`。

## 返回
【屏蔽数组】输入数组的修改版本，根据 `axis` 参数的值进行屏蔽。

### 代码#1
```py
# Python program explaining
# numpy.ma.mask_rowcols() function

# importing numpy as geek   
# and numpy.ma module as ma 
import numpy as geek 
import numpy.ma as ma

arr = geek.zeros((4, 4), dtype = int)
arr[2, 2] = 1

arr = ma.masked_equal(arr, 1)

gfg = ma.mask_rowcols(arr)

print (gfg)
```

**输出:**
```py
[[0 0 -- 0]
 [0 0 -- 0]
 [-- -- -- --]
 [0 0 -- 0]]
```

### 代码#2
```py
# Python program explaining
# numpy.ma.mask_rowcols() function

# importing numpy as geek   
# and numpy.ma module as ma 
import numpy as geek 
import numpy.ma as ma

arr = geek.zeros((5, 5), dtype = int)
arr[3, 3] = 1

arr = ma.masked_equal(arr, 1)

gfg = ma.mask_rowcols(arr)

print (gfg)
```

**输出:**
```py
[[0 0 0 -- 0]
 [0 0 0 -- 0]
 [0 0 0 -- 0]
 [-- -- -- -- --]
 [0 0 0 -- 0]]
```