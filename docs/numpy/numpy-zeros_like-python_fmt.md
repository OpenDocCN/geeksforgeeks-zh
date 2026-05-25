# Python 中的 `numpy.zeros_like()`

> 原文: [https://www.geeksforgeeks.org/numpy-zeros_like-python/](https://www.geeksforgeeks.org/numpy-zeros_like-python/)

这个 `numpy` 方法返回一个给定形状和类型的数组作为给定数组，并带有零。

```py
Syntax: numpy.zeros_like(array, dtype = None, order = 'K', subok = True)
```

## 参数

```py
array : array_like input
subok  : [optional, boolean]If true, then newly created array will be sub-class of array; 
                 otherwise, a base-class array
order  : C_contiguous or F_contiguous
         C-contiguous order in memory(last index varies the fastest)
         C order means that operating row-rise on the array will be slightly quicker
         FORTRAN-contiguous order in memory (first index varies the fastest).
         F order means that column-wise operations will be faster. 
dtype  : [optional, float(byDeafult)] Data type of returned array.  
```

## 返回值

```py
ndarray of zeros having given shape, order and datatype.
```

## 代码示例 1

```py
# Python Programming illustrating
# numpy.zeros_like method

import numpy as geek

array = geek.arange(10).reshape(5, 2)
print("Original array : \n", array)

b = geek.zeros_like(array, float)
print("\nMatrix b : \n", b)

array = geek.arange(8)
c = geek.zeros_like(array)
print("\nMatrix c : \n", c)
```

**输出:**

```py
Original array : 
 [[0 1]
 [2 3]
 [4 5]
 [6 7]
 [8 9]]

Matrix b : 
 [[ 0.  0.]
 [ 0.  0.]
 [ 0.  0.]
 [ 0.  0.]
 [ 0.  0.]]

Matrix c : 
 [0 0 0 0 0 0 0 0]
```

## 代码示例 2

```py
# Python Programming illustrating
# numpy.zeros_like method

import numpy as geek

array = geek.arange(10).reshape(5, 2)
print("Original array : \n", array)

array = geek.arange(4).reshape(2, 2)
c = geek.zeros_like(array, dtype = 'float')
print("\nMatrix  : \n", c)

array = geek.arange(8)
c = geek.zeros_like(array, dtype = 'float', order ='C')
print("\nMatrix  : \n", c)
```

**输出:**

```py
Original array : 
 [[0 1]
 [2 3]
 [4 5]
 [6 7]
 [8 9]]

Matrix  : 
 [[ 0.  0.]
 [ 0.  0.]]

Matrix  : 
 [ 0.  0.  0.  0.  0.  0.  0.  0.]
```

## 参考文献
[https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.zeros_like.html#numpy.zeros_like](https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.zeros_like.html#numpy.zeros_like)

**注意:**
同样，这些代码不会在 online-ID 上运行。请在您的系统上运行它们来探索工作方式。

本文由 **Mohit Gupta_OMG** 供稿😀。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。