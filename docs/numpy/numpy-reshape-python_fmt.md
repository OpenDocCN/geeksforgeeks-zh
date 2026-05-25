# Python 中的 `numpy.reshape()`

> 哎哎哎:# t0]https://www . geeksforgeeks . org/num py-reshape-python/

函数的作用是:在不改变数组数据的情况下，对数组进行整形。

```py
Syntax: numpy.reshape(array, shape, order = 'C')
```

**参数:**

```py
array : [array_like]Input array
shape : [int or tuples of int] e.g. if we are aranging an array with 10 elements then shaping
        it like numpy.reshape(4, 8) is wrong; we can do numpy.reshape(2, 5) or (5, 2)
order  : [C-contiguous, F-contiguous, A-contiguous; optional]         
         C-contiguous order in memory(last index varies the fastest)
         C order means that operating row-rise on the array will be slightly quicker
         FORTRAN-contiguous order in memory (first index varies the fastest).
         F order means that column-wise operations will be faster. 
         ‘A’ means to read / write the elements in Fortran-like index order if,
         array is Fortran contiguous in memory, C-like order otherwise
```

**返回:**

```py
Array which is reshaped without changing the data.
```

## 计算机编程语言

```py
# Python Program illustrating
# numpy.reshape() method

import numpy as geek

#array = geek.arrange(8) # The 'numpy' module has no attribute 'arrange'
array1 = geek.arrange(8)
print("Original array : \n", array1)

# shape array with 2 rows and 4 columns
array2 = geek.arrange(8).reshape(2, 4)
print("\narray reshaped with 2 rows and 4 columns : \n", array2)

# shape array with 4 rows and 2 columns
array3 = geek.arrange(8).reshape(4 ,2)
print("\narray reshaped with 2 rows and 4 columns : \n", array3)

# Constructs 3D array
array4 = geek.arrange(8).reshape(2, 2, 2)
print("\nOriginal array reshaped to 3D : \n", array4)
```

**输出:**

```py
Original array : 
 [0 1 2 3 4 5 6 7]

array reshaped with 2 rows and 4 columns : 
 [[0 1 2 3]
 [4 5 6 7]]

array reshaped with 4 rows and 2 columns : 
 [[0 1]
 [2 3]
 [4 5]
 [6 7]]

Original array reshaped to 3D : 
 [[[0 1]
  [2 3]]

[[4 5]
  [6 7]]]
```

**参考文献:**

*   [https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.reshape.html](https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.reshape.html)

**注意:**这些代码不会在 online-ID 上运行。请在您的系统上运行它们来探索工作。

本文由**莫希特·古普塔 _OMG 供稿😀**。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。