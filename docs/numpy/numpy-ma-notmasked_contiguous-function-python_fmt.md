# numpy.ma.notmasked_contiguous 函数 | Python

> 原文: [https://www.geeksforgeeks.org/numpy-ma-notmasked_contiguous-function-python/](https://www.geeksforgeeks.org/numpy-ma-notmasked_contiguous-function-python/)

`numpy.ma.notmasked_contiguous()` 函数沿着给定的轴查找掩码数组中连续的未掩码数据。

> **语法:** `numpy.ma.notmasked_contiguous(arr, axis=None)`
>
> **参数:**
> - `arr`: 【array_like】输入数组。
> - `axis`: 【int, 可选】执行操作的轴。默认值为 `None`。
>
> **返回:** 【list】数组中未屏蔽索引的切片（开始和结束索引）列表。如果输入是 2d，并且指定了轴，则结果是列表的列表。

## 代码示例 1

```py
# Python program explaining
# numpy.ma.notmasked_contiguous() function

# importing numpy as geek   
# and numpy.ma module as ma 
import numpy as geek 
import numpy.ma as ma

arr = geek.arange(12).reshape((3, 4))
mask = geek.zeros_like(arr)
mask[1:, :-1] = 1; mask[0, 1] = 1; mask[-1, 0] = 0
ma = geek.ma.array(arr, mask = mask)

gfg = geek.ma.notmasked_contiguous(ma)

print (gfg)
```

**输出:**

> `[slice(0, 1, None), slice(2, 4, None), slice(7, 9, None), slice(11, 12, None)]`

## 代码示例 2

```py
# Python program explaining
# numpy.ma.notmasked_contiguous() function

# importing numpy as geek   
# and numpy.ma module as ma 
import numpy as geek 
import numpy.ma as ma

arr = geek.arange(12).reshape((3, 4))
mask = geek.zeros_like(arr)
mask[1:, :-1] = 1; mask[0, 1] = 1; mask[-1, 0] = 0
ma = geek.ma.array(arr, mask = mask)

gfg = geek.ma.notmasked_contiguous(ma, axis = 1)

print (gfg)
```

**输出:**

> `[[slice(0, 1, None), slice(2, 4, None)], [slice(3, 4, None)], [slice(0, 1, None), slice(3, 4, None)]]`