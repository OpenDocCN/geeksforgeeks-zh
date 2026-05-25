# Numpy maskedarray . var()函数 | Python

> 原文: [https://www.geeksforgeeks.org/numpy-maskedarray-var-function-python/](https://www.geeksforgeeks.org/numpy-maskedarray-var-function-python/)

`numpy.ma.var()`函数用于计算沿指定轴的方差。它返回被屏蔽的数组元素的方差，这是一个分布范围的度量。默认情况下，计算展平数组的方差，否则计算指定轴的方差。

> **语法:** `numpy.ma.var(arr, axis=None, dtype=None, out=None, ddof=0, keepdims=False)`
> **参数:**
> `arr`: 【ndarray】输入屏蔽数组。
> `axis`: 【int，可选】计算方差的轴。默认值(`None`)是计算展平数组的方差。
> `dtype`: 【data-type，可选】返回数组的类型，以及元素相乘的累加器的类型。
> `out`: 【ndarray，可选】存储结果的位置。
> - >如果提供，它必须具有输入广播到的形状。
> - >如果未提供或`None`，则返回新分配的数组。
> `ddof`: 【int，可选】“δ自由度”:计算中使用的除数为`N - ddof`，其中`N`代表元素个数。默认情况下，`ddof`为零。
> `keepdims`: 【bool，可选】如果设置为`True`，则缩小的轴作为尺寸为1的维度留在结果中。使用此选项，结果将根据输入数组正确广播。
> **Return :** 【variance_along_axis, ndarray】除非指定`out`，否则将返回一个保存结果的新数组，在这种情况下，将返回对`out`的引用。

**代码#1 :**

## 代码示例1

```py
# Python program explaining
# numpy.MaskedArray.var() method

# importing numpy as geek 
# and numpy.ma module as ma
import numpy as geek
import numpy.ma as ma

# creating input array 
in_arr = geek.array([[1, 2], [ 3, -1], [ 5, -3]])
print ("Input array : ", in_arr)

# Now we are creating a masked array.
# by making  entry as invalid. 
mask_arr = ma.masked_array(in_arr, mask =[[1, 0], [ 1, 0], [ 0, 0]])
print ("Masked array : ", mask_arr)

# applying MaskedArray.var   
# methods to masked array
out_arr = ma.var(mask_arr)
print ("variance of masked array along default axis : ", out_arr)
```

**Output:**

```py
Input array :  [[ 1  2]
 [ 3 -1]
 [ 5 -3]]
Masked array :  [[-- 2]
 [-- -1]
 [5 -3]]
variance of masked array along default axis :  9.1875
```

**代码#2 :**

## 代码示例2

```py
# Python program explaining
# numpy.MaskedArray.var() method

# importing numpy as geek 
# and numpy.ma module as ma
import numpy as geek
import numpy.ma as ma

# creating input array
in_arr = geek.array([[1, 0, 3], [ 4, 1, 6]])
print ("Input array : ", in_arr)

# Now we are creating a masked array.
# by making one entry as invalid. 
mask_arr = ma.masked_array(in_arr, mask =[[ 0, 0, 0], [ 0, 0, 1]])
print ("Masked array : ", mask_arr)

# applying MaskedArray.var methods
# to masked array
out_arr1 = ma.var(mask_arr, axis = 0)
print ("variance of masked array along 0 axis : ", out_arr1)

out_arr2 = ma.var(mask_arr, axis = 1)
print ("variance of masked array along 1 axis : ", out_arr2)
```

**输出:**

```py
Input array :  [[1 0 3]
 [4 1 6]]
Masked array :  [[1 0 3]
 [4 1 --]]
variance of masked array along 0 axis :  [2.25 0.25 0.  ]
variance of masked array along 1 axis :  [1.55555556 2.25      ]
```