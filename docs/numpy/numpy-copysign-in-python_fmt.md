# numpy.copysign() 函数详解

> 原文链接: https://www.geeksforgeeks.org/numpy-copysign-in-python/

`numpy.copysign(arr1, arr2, out=None, where=True, casting='same_kind', order='K', dtype=None)` 是一个数学函数，用于将 `arr1` 的符号变为 `arr2` 的符号。`arr1` 或 `arr2` 都可以是列表、序列或标量值。如果两者都是数组，则它们必须具有相同的维度；否则 `arr2` 可以是一个标量值。

## 参数

- **arr1**: 【array_like】输入数组，其数值将被改变符号。
- **arr2**: 【array_like】输入数组，提供新的符号值。
- **out**: 【ndarray, optional】输出数组，与输入数组尺寸相同，用于存放结果。
- ****kwargs**: 允许传递关键字可变长度参数给函数。用于处理函数中的命名参数。
- **where**: 【array_like, optional】布尔值，`True` 表示在对应位置计算通用函数（ufunc），`False` 表示将输出中的对应值保留。

## 返回值

返回一个数组，其值与 `arr1` 相同，但符号与 `arr2` 相同。

## 代码示例

### 示例 1

```py
# Python program illustrating 
# copysign() method 
import numpy as np

arr1 = [1, -23, +34, 11]
arr2 = [-1, 2, -3, -4]

print ("arr1 : ", arr1)
print ("arr2 : ", arr2)

print ("\nCheck sign of arr1 : ", np.signbit(arr1))
print ("\nCheck sign of arr2 : ", np.signbit(arr1))
print ("\nCheck for copysign : ", np.signbit(np.copysign(arr1, arr2)))
```

**输出:**

```py
arr1 :  [1, -23, 34, 11]
arr2 :  [-1, 2, -3, -4]

Check sign of arr1 :  [False  True False False]
Check sign of arr2 :  [False  True False False]
Check for copysign :  [ True False  True  True]
```

### 示例 2

```py
# Python program illustrating 
# copysign() method 
import numpy as np

arr1 = [1, -23, +34, 11]

print ("\nCheck sign of arr2 : ", np.signbit(arr1))
print ("\nCheck for copysign : ", np.signbit(np.copysign(arr1, -3)))
```

**输出:**

```py
Check sign of arr2 :  [False  True False False]
Check for copysign :  [ True  True  True  True]
```