# numpy.conj()

> 原文链接: https://www.geeksforgeeks.org/numpy-conj-in-python/

`numpy.conj()` 函数用于计算任意复数的共轭。

复数的共轭是通过改变其虚部的符号得到的。例如，如果复数是 `2+5j`，那么它的共轭是 `2-5j`。

## 语法

`numpy.conj(x, out=None, ufunc 'conjugate')`

## 参数

- `x`: array_like，输入值。
- `out`: ndarray，可选。输出数组与输入数组具有相同的尺寸，用于存放结果。

## 返回值

- `x`: ndarray。输入 `x` 的复共轭，与输入具有相同的数据类型。

## 代码示例

**示例 1：**

```py
# Python3 code demonstrate conj() function

#importing numpy
import numpy as np

in_complx1 = 2+4j
out_complx1 = np.conj(in_complx1)
print ("Output conjugated complex number of  2+4j : ", out_complx1)

in_complx2 =5-8j
out_complx2 = np.conj(in_complx2)
print ("Output conjugated complex number of 5-8j: ", out_complx2)
```

**输出：**

```py
Output conjugated complex number of  2+4j :  (2-4j)
Output conjugated complex number of 5-8j:  (5+8j)
```

**示例 2：**

```py
# Python3 code demonstrate conj() function

# importing numpy
import numpy as np

in_array = np.eye(2) + 3j * np.eye(2)
print ("Input array : ", in_array)

out_array = np.conjugate(in_array)
print ("Output conjugated array : ", out_array)
```

**输出：**

```py
Input array :  [[ 1.+3.j  0.+0.j]
 [ 0.+0.j  1.+3.j]]
Output conjugated array :  [[ 1.-3.j  0.-0.j]
 [ 0.-0.j  1.-3.j]]
```