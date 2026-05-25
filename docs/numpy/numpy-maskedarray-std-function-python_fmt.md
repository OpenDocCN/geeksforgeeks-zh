# NumPy MaskedArray.std() 函数 | Python

> 原文：[https://www.geeksforgeeks.org/numpy-maskedarray-std-function-python/](https://www.geeksforgeeks.org/numpy-maskedarray-std-function-python/)

## 函数介绍

`numpy.MaskedArray.std()` 函数用于计算沿指定轴的标准差。这里屏蔽的条目被忽略。默认情况下，计算展平数组的标准差，否则计算指定轴的标准差。

## 语法与参数

**语法：**
`numpy.ma.std(arr, axis=None, dtype=None, out=None, ddof=0, keepdims=False)`

**参数：**

- `arr`：【ndarray】输入屏蔽数组。
- `axis`：【int，可选】计算标准差的轴。
- `dtype`：【dtype，可选】返回数组的类型，以及元素相乘的累加器的类型。
- `out`：【ndarray，可选】存储结果的位置。
    - 如果提供，它必须具有输入广播到的形状。
    - 如果未提供或 `None`，则返回新分配的数组。
- `ddof`：【int，可选】“δ自由度”：计算中使用的除数为 `N - ddof`，其中 `N` 代表元素个数。默认情况下，`ddof` 为零。
- `keepdims`：【bool，可选】如果设置为 `True`，减少的轴将作为尺寸为 1 的维度留在结果中。使用此选项，结果将根据输入数组正确广播。

**返回值：**
【standard_deviation_along_axis, ndarray】除非指定 `out`，否则将返回一个保存结果的新数组，在这种情况下，将返回对 `out` 的引用。

## 代码示例

### 代码 #1

```py
# Python program explaining
# numpy.MaskedArray.std() method

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

# applying MaskedArray.std     
# methods to masked array
out_arr = ma.std(mask_arr) 
print ("standard deviation of masked array along default axis : ", out_arr) 
```

**输出：**

```py
Input array :  [[ 1  2]
 [ 3 -1]
 [ 5 -3]]
Masked array :  [[-- 2]
 [-- -1]
 [5 -3]]
standard deviation of masked array along default axis :  3.031088913245535
```

### 代码 #2

```py
# Python program explaining
# numpy.MaskedArray.std() method

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

# applying MaskedArray.std methods 
# to masked array
out_arr1 = ma.std(mask_arr, axis = 0) 
print ("standard deviation of masked array along 0 axis : ", out_arr1)

out_arr2 = ma.std(mask_arr, axis = 1) 
print ("standard deviation of masked array along 1 axis : ", out_arr2)
```

**输出：**

```py
Input array :  [[1 0 3]
 [4 1 6]]

Masked array :  [[1 0 3]
 [4 1 --]]

standard deviation of masked array along 0 axis :  [1.5 0.5 0.0]

standard deviation of masked array along 1 axis :  [1.247219128924647 1.5]
```