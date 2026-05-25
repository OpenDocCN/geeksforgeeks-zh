# Python 中的 `numpy.squeeze()`

> 原文: [https://www.geeksforgeeks.org/numpy-squeeze-in-python/](https://www.geeksforgeeks.org/numpy-squeeze-in-python/)

`numpy.squeeze()` 函数用于从数组的形状中移除长度为 1 的维度。

## 语法

`numpy.squeeze(arr, axis=None)`

## 参数

- `arr`：【ndarray】输入数组。
- `axis`：【None 或 int 或 int 元组，可选】选择形状中一维条目的子集。如果所选轴的形状条目大于 1，则会引发错误。

## 返回值

`squeeze`：【ndarray】输入数组，但长度为 1 的维度的全部或子集被移除。这永远是一个数组本身或一个视图。

## 代码示例 1

```py
# Python program explaining
# numpy.squeeze function

import numpy as geek

in_arr = geek.array([[[2, 2, 2], [2, 2, 2]]])

print ("Input array : ", in_arr)
print("Shape of input array : ", in_arr.shape)

out_arr = geek.squeeze(in_arr)

print ("output squeezed array : ", out_arr)
print("Shape of output array : ", out_arr.shape)
```

**输出:**

```py
Input array :  [[[2 2 2]
  [2 2 2]]]
Shape of input array :  (1, 2, 3)
output squeezed array :  [[2 2 2]
 [2 2 2]]
Shape of output array :  (2, 3)
```

## 代码示例 2

```py
# Python program explaining
# numpy.squeeze function
import numpy as geek
in_arr = geek.arange(9).reshape(1, 3, 3)

print ("Input array : ", in_arr)
out_arr = geek.squeeze(in_arr, axis = 0)

print ("output array : ", out_arr)
print("The shapes of Input and Output array : ")

print(in_arr.shape, out_arr.shape)
```

**输出:**

```py
Input array :  [[[0 1 2]
  [3 4 5]
  [6 7 8]]]
output array :  [[0 1 2]
 [3 4 5]
 [6 7 8]]
The shapes of Input and Output array :
(1, 3, 3) (3, 3)
```

## 注意

```py
ValueError :
If axis is not None, and an axis being squeezed is not of length 1.
```

## 代码示例 3

```py
# Python program explaining
# numpy.squeeze function
# when value error occurs
import numpy as geek

in_arr = geek.arange(9).reshape(1, 3, 3)

print ("Input array : ", in_arr)
out_arr = geek.squeeze(in_arr, axis = 1)

print ("output array : ", out_arr)
print("The shapes of Input and Output array : ")

print(in_arr.shape, out_arr.shape)
```

**输出:**

```py
ValueError                                Traceback (most recent call last)
 in ()

6 print ("Input array : ", in_arr)
----> 7 out_arr = geek.squeeze(in_arr, axis=1)
      8 print ("output array : ", out_arr)
      9 print("The shapes of Input and Output array : ")

~\Anaconda3\lib\site-packages\numpy\core\fromnumeric.py in squeeze(a, axis)
   1196     try:
   1197         # First try to use the new axis= parameter
-> 1198         return squeeze(axis=axis)
   1199     except TypeError:
   1200         # For backwards compatibility

ValueError: cannot select an axis to squeeze out which has size not equal to one
```