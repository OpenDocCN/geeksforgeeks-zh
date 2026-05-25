# numpy.ndarray.dot() 函数 | Python

> 原文: `https://www.geeksforgeeks.org/numpy-ndarray-dot-function-python/`

`numpy.ndarray.dot()` 函数返回两个数组的点积。

## 语法
`numpy.ndarray.dot(arr, out=None)`

## 参数
- `arr` : 【array_like】输入数组。
- `out` : 【ndarray，可选】输出参数。

## 返回
【ndarray】两个数组的点积。

**代码#1 :**

```py
# Python program explaining
# numpy.ndarray.dot() function

# importing numpy as geek 
import numpy as geek

arr1 = geek.eye(3)
arr = geek.ones((3, 3)) * 3

gfg = arr1.dot( arr )

print( gfg)
```

**输出:**

```py
[[ 3.  3.  3.]
 [ 3.  3.  3.]
 [ 3.  3.  3.]]
```

**代码#2 :**

```py
# Python program explaining
# numpy.ndarray.dot() function

# importing numpy as geek 
import numpy as geek

arr1 = geek.eye(3)
arr = geek.ones((3, 3)) * 3

gfg = arr1.dot(arr).dot(arr)

print( gfg)
```

**输出:**

```py
[[ 27.  27.  27.]
 [ 27.  27.  27.]
 [ 27.  27.  27.]]
```