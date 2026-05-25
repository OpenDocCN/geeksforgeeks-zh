# Python 中的 `numpy.logical_or()`

> 原文: [https://www.geeksforgeeks.org/numpy-logical_or-python/](https://www.geeksforgeeks.org/numpy-logical_or-python/)

## 函数签名

`numpy.logical_or(arr1, arr2, out=None, where=True, casting='same_kind', order='K', dtype=None, ufunc 'logical_or')`：这是一个逻辑函数，它帮助用户逐元素找出 `arr1` **OR** `arr2` 的真值。两个数组必须具有相同的形状。

## 参数

- `arr1`: 【array_like】输入数组。
- `arr2`: 【array_like】输入数组。
- `out`: 【ndarray，可选】输出数组，与输入数组具有相同的尺寸，与结果一起放置。
- `**kwargs`: 允许您将关键字可变长度的参数传递给函数。当我们想要处理函数中的命名参数时，会用到它。
- `where`: 【array_like，可选】`True` 值表示计算该位置的通用函数(`ufunc`)，`False` 值表示将值单独留在输出中。

## 返回值

一个包含 `arr1` 与 `arr2` 逐元素进行逻辑或运算后布尔结果的数组（形状相同）。

## 代码示例

### 代码 1：工作示例

```py
# Python program explaining
# logical_or() function
import numpy as np

# input
arr1 = [1, 3, False, 4]
arr2 = [3, 0, True, False]

# output
out_arr = np.logical_or(arr1, arr2)

print ("Output Array : ", out_arr)
```

**输出:**

```py
Output Array :  [ True  True  True  True]
```

### 代码 2：如果输入数组的形状不同，则值错误

```py
# Python program explaining
# logical_or() function
import numpy as np

# input
arr1 = [8, 2, False, 4]
arr2 = [3, 0, False, False, 8]

# output
out_arr = np.logical_or(arr1, arr2)

print ("Output Array : ", out_arr)
```

**输出:**

```py
ValueError: operands could not be broadcast together with shapes (4,) (5,)
```

## 参考文献

[https://docs.scipy.org/doc/numpy-1.13.0/reference/generated/numpy.logical_or.html#numpy.logical_or](https://docs.scipy.org/doc/numpy-1.13.0/reference/generated/numpy.logical_or.html#numpy.logical_or)