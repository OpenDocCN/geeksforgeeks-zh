# numpy.ma.MaskedArray.count() 函数 – Python

> 原文: [https://www.geeksforgeeks.org/numpy-ma-maskedarray-count-function-python/](https://www.geeksforgeeks.org/numpy-ma-maskedarray-count-function-python/)

`numpy.ma.MaskedArray.count()` 函数沿着给定的轴计算数组中未被屏蔽的元素。

## 语法
`numpy.ma.MaskedArray.count(self, axis=None, keepdims=no_value)`

## 参数
- **axis**: 【无或整数或整数元组，可选】执行计数的轴。默认轴为 `None`，在输入数组的所有维度上执行计数。轴可以是负的，在这种情况下，它从最后一个轴计数到第一个轴。
- **keepdims**: 【bool，可选】如果设置为 `True`，缩小的轴将作为尺寸为 1 的维度留在结果中。使用此选项，结果将针对原数组正确广播。

## 返回值
【ndarray 或标量】一个与输入数组形状相同的数组，去掉了指定的轴。如果数组是 0-d 数组，或者如果 `axis` 是 `None`，则返回标量。

## 代码示例

**代码#1：**

```py
# Python program explaining
# numpy.ma.MaskedArray.count() function

# importing numpy as geek   
# and numpy.ma module as ma  
import numpy as geek  
import numpy.ma as ma

arr = ma.arange(6).reshape((2, 3))
arr[1, :] = ma.masked

gfg = arr.count(axis = 0)

print (gfg)
```

**输出:**

```py
[1 1 1]
```

**代码#2：**

```py
# Python program explaining
# numpy.ma.MaskedArray.count() function

# importing numpy as geek   
# and numpy.ma module as ma  
import numpy as geek  
import numpy.ma as ma

arr = ma.arange(6).reshape((2, 3))
arr[1, :] = ma.masked

gfg = arr.count()

print (gfg)
```

**输出:**

```py
3
```