# numpy.nancumprod() in Python

> 原文链接: https://www.geeksforgeeks.org/numpy-nancumprod-in-python/

`numpy.nancumprod()` 函数用于计算给定轴上数组元素的累计乘积，不将不是一个数字（NaN）视为一。当遇到新的 NaN 时，累积积不变，领先的 NaN 被新的 NaN 取代。对于全为 NaN 或空的切片，返回 1。

## 语法

`numpy.nancumprod(arr, axis=None, dtype=None, out=None)`

## 参数

- `arr`: 【array_like】包含需要求和的数字的数组。如果 `arr` 不是数组，则尝试转换。
- `axis`: 计算累积积的轴。默认情况下，计算展平数组的乘积。
- `dtype`: 返回数组的类型，以及元素相乘的累加器的类型。如果未指定 `dtype`，则默认为 `arr` 的 `dtype`，除非 `arr` 具有精度小于默认平台整数的整数 `dtype`。在这种情况下，将使用默认的平台整数。
- `out`: 【ndarray，可选】存储结果的位置。
    - 如果提供，它必须具有输入广播到的形状。
    - 如果未提供或为 `None`，则返回新分配的数组。

## 返回值

除非指定 `out`，否则将返回一个保存结果的新数组，在这种情况下，将返回该数组。

## 代码示例

### 代码 #1：工作示例

```py
# Python program explaining
# numpy.nancumprod() function

import numpy as geek
in_num = 10

print ("Input number : ", in_num)

out_prod = geek.nancumprod(in_num)
print ("cumulative product of input number : ", out_prod)
```

**输出:**

```py
Input number :  10
cumulative product of input number :  [10]
```

### 代码 #2

```py
# Python program explaining
# numpy.nancumprod() function

import numpy as geek

in_arr = geek.array([[2, 2, 2], [2, 2, geek.nan]])

print ("Input array : ", in_arr)

out_prod = geek.nancumprod(in_arr)
print ("cumulative product of array elements: ", out_prod)
```

**输出:**

```py
Input array :  [[  2.   2.   2.]
 [  2.   2.  nan]]
cumulative product of array elements:  [  2.   4.   8.  16.  32.  32.]
```

### 代码 #3

```py
# Python program explaining
# numpy.nancumprod() function

import numpy as geek

in_arr = geek.array([[2, 2, 2], [2, 2, geek.nan]])

print ("Input array : ", in_arr)

out_prod = geek.nancumprod(in_arr, axis = 1)
print ("cumulative product of array elements taking axis 1: ", out_prod)
```

**输出:**

```py
Input array :  [[  2.   2.   2.]
 [  2.   2.  nan]]
cumulative product of array elements taking axis 1:  [[ 2.  4.  8.]
 [ 2.  4.  4.]]
```