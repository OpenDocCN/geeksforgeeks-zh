# numpy.ma.flatnotmasked_contiguous()函数

> 原文: [https://www.geeksforgeeks.org/numpy-ma-flatnotmasked_contiguous-function-python/](https://www.geeksforgeeks.org/numpy-ma-flatnotmasked_contiguous-function-python/)

`numpy.ma.flatnotmasked_contiguous()`函数沿给定轴查找掩码数组中连续的未掩码数据。

> **语法:** `numpy.ma.flatnotmasked_contiguous(arr)`
> **参数:**
> **arr:** 【array_like】输入数组。
> **返回:** 【slice_list】切片对象的排序序列(开始索引、结束索引)。

## Python

**代码#1 :**

```py
# Python program explaining
# numpy.ma.flatnotmasked_contiguous() function

# importing numpy as geek 
# and numpy.ma module as ma
import numpy as geek
import numpy.ma as ma

arr = geek.ma.arange(8)

gfg = geek.ma.flatnotmasked_contiguous(arr)

print (gfg)
```

**输出:**

```py
slice(0, 8, None)
```

**代码#2 :**

```py
# Python program explaining
# numpy.ma.flatnotmasked_contiguous() function

# importing numpy as geek 
# and numpy.ma module as ma
import numpy as geek
import numpy.ma as ma

arr = geek.ma.arange(12)

gfg = geek.ma.flatnotmasked_contiguous(arr)

print (gfg)
```

**输出:**

```py
slice(0, 12, None)
```