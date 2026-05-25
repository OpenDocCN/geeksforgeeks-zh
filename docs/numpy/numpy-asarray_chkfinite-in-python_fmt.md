# Python 中的 `numpy.asarray_chkfinite()`

> 原文: [https://www.geeksforgeeks.org/numpy-asarray_chkfinite-in-python/](https://www.geeksforgeeks.org/numpy-asarray_chkfinite-in-python/)

`numpy.asarray_chkfinite()` 函数用于在需要将输入转换为数组时，检查 NaNs（非数字）或 Infs（无穷大）。输入可以是标量、列表、元组、嵌套序列或数组。

## 语法

`numpy.asarray_chkfinite(arr, dtype=None, order=None)`

## 参数

- **arr**: 【array_like】输入数据，可以是任何能转换为浮点型数组的形式。这包括标量、列表、元组、嵌套序列和数组。
- **dtype**: 【data-type, optional】数据类型。默认情况下，数据类型是从输入数据中推断出来的。
- **order**: 【{'C', 'F'}, optional】内存布局，使用行主序（C 风格）还是列主序（Fortran 风格）。默认为 'C'。

## 返回值

- **【ndarray】** 输入 `arr` 的数组解释。如果输入已经是数组，则不执行复制。如果 `arr` 是 `ndarray` 的子类，则返回基类 `ndarray`。

## 代码示例

### 代码#1: 列表到数组

```python
# Python program explaining
# numpy.asarray_chkfinite() function

import numpy as geek
my_list = [1, 3, 5, 7, 9]

print("Input list : ", my_list)

out_arr = geek.asarray_chkfinite(my_list, dtype='float')
print("output array from input list : ", out_arr)
```

**输出:**

```
Input list :  [1, 3, 5, 7, 9]
output array from input list :  [ 1.  3.  5.  7.  9.]
```

### 代码#2: 元组到数组

```python
# Python program explaining
# numpy.asarray_chkfinite() function

import numpy as geek

my_tuple = ([1, 3, 9], [8, 2, 6])

print("Input tuple : ", my_tuple)

out_arr = geek.asarray_chkfinite(my_tuple, dtype='int8')
print("output array from input tuple : ", out_arr)
```

**输出:**

```
Input tuple :  ([1, 3, 9], [8, 2, 6])
output array from input tuple :  [[1 3 9]
 [8 2 6]]
```

## 注意

如果 `arr` 包含 `NaN`（非数字）或 `Inf`（无穷大），`numpy.asarray_chkfinite()` 函数会引发 `ValueError`。

### 代码#3: 值错误示例

```python
# Python program explaining
# numpy.asarray_chkfinite() function
# when value error occurs

import numpy as geek

my_list = [1, 3, 5, 7, geek.inf, geek.nan]

print("Input list : ", my_list)

out_arr = geek.asarray_chkfinite(my_list)
print("output array from input list : ", out_arr)
```

**输出:**

```
ValueError: array must not contain infs or NaNs
```