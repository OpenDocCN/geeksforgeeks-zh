# `numpy.MaskedArray.ravel()` 函数 | Python

> 原文: [https://www.geeksforgeeks.org/numpy-maskedarray-ravel-function-python/](https://www.geeksforgeeks.org/numpy-maskedarray-ravel-function-python/)

`numpy.MaskedArray.ravel()` 函数用于返回一个 1D 版本的自身掩码数组视图。

> **语法:** `numpy.ma.ravel(self, order='C')`
>
> **参数:**
> **order**: [`'C'`, `'F'`, `'A'`, `'K'`，可选] 默认使用 `'C'` 索引顺序。
> - 使用此索引顺序读取元素。
> - `'C'` 表示以类 C 顺序索引元素，最后一个轴索引变化最快，回到第一个轴索引变化最慢。
> - `'F'` 表示以类似 Fortran 的索引顺序对元素进行索引，第一个索引变化最快，最后一个索引变化最慢。
> - `'A'` 表示以类似 Fortran 的索引顺序读取元素，如果 `m` 在内存中是 Fortran 连续的，则以类似 C 的顺序读取。
> - `'K'` 表示按照元素在内存中出现的顺序读取元素，除了当步长为负时反转数据。
>
> **返回:** [`MaskedArray`] 展平的 1D 掩码数组。

## 代码示例 1

```py
# Python program explaining
# numpy.MaskedArray.ravel() method

# importing numpy as geek   
# and numpy.ma module as ma 
import numpy as geek 
import numpy.ma as ma

# creating input array   
in_arr = geek.array([[1, 2], [ 3, -1]]) 
print ("Input array : ", in_arr)

# Now we are creating a masked array. 
# by making two entry as invalid.   
mask_arr = ma.masked_array(in_arr, mask =[[0, 1], [ 1, 0]]) 
print ("Masked array : ", mask_arr)

# applying MaskedArray.ravel methods to mask array 
out_arr = mask_arr.ravel() 
print ("1D view of masked array : ", out_arr) 
```

**输出:**

```py
Input array :  [[ 1  2]
 [ 3 -1]]
Masked array :  [[1 --]
 [-- -1]]
1D view of masked array :  [1 -- -- -1]
```

## 代码示例 2

```py
# Python program explaining
# numpy.MaskedArray.ravel() method

# importing numpy as geek   
# and numpy.ma module as ma 
import numpy as geek 
import numpy.ma as ma

# creating input array 
in_arr = geek.array([[[ 2e8, 3e-5]], [[ -45.0, 2e5]]])
print ("Input array : ", in_arr)

# Now we are creating a masked array. 
# by making one entry as invalid.   
mask_arr = ma.masked_array(in_arr, mask =[[[ 1, 0]], [[ 0, 0]]]) 
print ("3D Masked array : ", mask_arr)

# applying MaskedArray.ravel methods to mask array 
out_arr = mask_arr.ravel() 
print ("1D view of masked array : ", out_arr) 
```

**输出:**

```py
Input array :  [[[ 2.0e+08  3.0e-05]]

[[-4.5e+01  2.0e+05]]]
3D Masked array :  [[[-- 3e-05]]

[[-45.0 200000.0]]]
1D view of masked array :  [-- 3e-05 -45.0 200000.0]
```