# numpy.logical_xor()

> 原文: [https://www.geeksforgeeks.org/numpy-logical_xor-python/](https://www.geeksforgeeks.org/numpy-logical_xor-python/)

`numpy.logical_xor(arr1, arr2, out=None, where=True, casting='same_kind', order='K', dtype=None, ufunc 'logical_xor')` 是一个逻辑函数，它帮助用户逐元素找出 `arr1` 的真值 **XOR** `arr2`。两个数组必须具有相同的形状。

## 参数

- `arr1`: 【array_like】输入数组。
- `arr2`: 【array_like】输入数组。
- `out`: 【ndarray，可选】输出数组，与输入数组具有相同的尺寸，与结果一起放置。
- `**kwargs`: 允许您将关键字可变长度的参数传递给函数。当我们想要处理函数中的命名参数时，会用到它。
- `where`: 【array_like，可选】`True` 值表示计算该位置的通用函数(`ufunc`)，`False` 值表示将值单独留在输出中。

## 返回值

一个包含 `arr1` 与 `arr2` 逐元素进行 XOR 运算的布尔结果的数组（形状相同）。

## 代码示例

### 代码 1：工作

```python
# Python program explaining
# logical_xor() function
import numpy as np

# input
arr1 = [1, 3, False, 0]
arr2 = [3, 0, True, False]

# output
out_arr = np.logical_xor(arr1, arr2)

print ("Output Array : ", out_arr)
```

**输出:**

```python
Output Array :  [False  True  True False]
```

### 代码 2：如果输入数组的形状不同，则值错误

```python
# Python program explaining
# logical_xor() function
import numpy as np

# input
arr1 = [8, 2, False, 4]
arr2 = [3, 0, False, False, 8]

# output
out_arr = np.logical_xor(arr1, arr2)

print ("Output Array : ", out_arr)
```

**输出:**

```python
ValueError: operands could not be broadcast together with shapes (4,) (5,)
```

### 代码 3：可以检查条件

```python
# Python program explaining
# logical_xor() function
import numpy as np

# input
arr1 = np.arange(8)
print ("arr1 : ", arr1)

print ("\narr1>3 : \n", arr1>3)
print ("\narr1<6 : \n", arr1<6)

print ("\nXOR Value  : \n", np.logical_xor(arr1>3, arr1<6))
```

**输出:**

```python
arr1 :  [0 1 2 3 4 5 6 7]

arr1>3 :
 [False False False False  True  True  True  True]

arr1<6 :
 [ True  True  True  True  True  True False False]

XOR Value  :
 [ True  True  True  True False False  True  True]
```

## 参考文献

[https://docs.scipy.org/doc/numpy-1.13.0/reference/generated/numpy.logical_xor.html#numpy.logical_xor](https://docs.scipy.org/doc/numpy-1.13.0/reference/generated/numpy.logical_xor.html#numpy.logical_xor)