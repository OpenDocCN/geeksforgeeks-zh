# numpy.ma.mask_rows()函数

> 原文: [https://www.geeksforgeeks.org/numpy-ma-mask_rows-function-python/](https://www.geeksforgeeks.org/numpy-ma-mask_rows-function-python/)

在这个函数中，屏蔽包含屏蔽值的2D数组的行。这个函数是`mask_rowcols`轴等于0的快捷方式。

> 语法: `numpy.ma.mask_rows(arr, axis=None)`
> 参数:
> `arr`: 【array_like, MaskedArray】要屏蔽的数组。结果是一个掩码数组。
> `axis`: 【int, 可选】执行操作的轴。默认值为`None`。
> 返回: 【MaskedArray】输入数组的修改版本。

### 代码示例1

```py
# Python program explaining
# numpy.ma.mask_rows() function

# importing numpy as geek
# and numpy.ma module as ma
import numpy as geek
import numpy.ma as ma

arr = geek.zeros((4, 4), dtype = int)
arr[2, 2] = 1

arr = ma.masked_equal(arr, 1)

gfg = ma.mask_rows(arr)

print (gfg)
```

输出:

```py
[[0 0 0 0]
 [0 0 0 0]
 [-- -- -- --]
 [0 0 0 0]]
```

### 代码示例2

```py
# Python program explaining
# numpy.ma.mask_rows() function

# importing numpy as geek
# and numpy.ma module as ma
import numpy as geek
import numpy.ma as ma

arr = geek.zeros((5, 5), dtype = int)
arr[3, 3] = 1

arr = ma.masked_equal(arr, 1)

gfg = ma.mask_rows(arr)

print (gfg)
```

输出:

```py
[[0 0 0 0 0]
 [0 0 0 0 0]
 [0 0 0 0 0]
 [-- -- -- -- --]
 [0 0 0 0 0]]
```