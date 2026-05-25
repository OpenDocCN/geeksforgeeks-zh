# Python 中 `numpy.intersect1d()` 函数

> 原文：[https://www.geeksforgeeks.org/numpy-intersect1d-function-in-python/](https://www.geeksforgeeks.org/numpy-intersect1d-function-in-python/)

## 函数介绍

`numpy.intersect1d()` 函数查找两个数组的交集，并返回两个输入数组中已排序的唯一值。

## 语法与参数

**语法：**
`numpy.intersect1d(arr1, arr2, assume_unique=False, return_indices=False)`

**参数：**
- `arr1`、`arr2`：【array_like】输入数组。
- `assume_unique`：【bool】如果为真，则输入数组都假设为唯一，这样可以加快计算速度。默认值为假。
- `return_indices`：【bool】如果为真，则返回两个数组交集对应的索引。如果有多个值，则使用值的第一个实例。默认值为假。

**返回：**【ndarray】常见和独特元素的排序 1D 数组。

## 代码示例

### 代码#1

```py
# Python program explaining
# numpy.intersect1d() function

# importing numpy as geek 
import numpy as geek

arr1 = geek.array([1, 1, 2, 3, 4])
arr2 = geek.array([2, 1, 4, 6])

gfg = geek.intersect1d(arr1, arr2)

print (gfg)
```

**输出：**

```py
[1 2 4]
```

### 代码#2

```py
# Python program explaining
# numpy.intersect1d() function

# importing numpy as geek 
import numpy as geek

arr1 = [1, 2, 3, 4, 5, 6, 7, 8, 9]
arr2 = [1, 3, 5, 7, 9]

gfg = geek.intersect1d(arr1, arr2)

print (gfg)
```

**输出：**

```py
[1 3 5 7 9]
```