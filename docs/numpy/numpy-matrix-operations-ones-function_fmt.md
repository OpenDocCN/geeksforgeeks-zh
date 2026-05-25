# NumPy 矩阵运算：`ones()` 函数

> 原文：[https://www.geeksforgeeks.org/numpy-matrix-operations-ones-function/](https://www.geeksforgeeks.org/numpy-matrix-operations-ones-function/)

`numpy.matlib.ones()` 是 NumPy 中用于矩阵运算的另一个功能。它返回一个给定形状和类型的矩阵，用 1 填充。

> **语法：** `numpy.matlib.ones(shape, dtype=None, order='C')`
>
> **参数：**
> - `shape`：【int 或 int 元组】输出矩阵的行数和列数。如果形状的长度为 1（即 `N`），或者是标量 `N`，则输出成为形状为 `(1, N)` 的单行矩阵。
> - `dtype`：【可选】所需输出数据类型。
> - `order`：在内存中是按行主序（C 风格）还是列主序（Fortran 风格）存储多维数据。
>
> **返回：** 给定形状、数据类型和顺序的矩阵。

## 代码示例 1

```py
# Python program explaining
# numpy.matlib.ones() function

# importing matrix library from numpy
import numpy as geek
import numpy.matlib

# desired 3 x 4 output matrix 
out_mat = geek.matlib.ones((3, 4)) 
print ("Output matrix : ", out_mat) 
```

**输出：**

```py
Output matrix :  [[ 1.  1.  1.  1.]
 [ 1.  1.  1.  1.]
 [ 1.  1.  1.  1.]]
```

## 代码示例 2

```py
# Python program explaining
# numpy.matlib.ones() function

# importing numpy and matrix library
import numpy as geek
import numpy.matlib

# desired 1 x 5 output matrix 
out_mat = geek.matlib.ones(shape = 5, dtype = int) 
print ("Output matrix : ", out_mat) 
```

**输出：**

```py
Output matrix :  [[1 1 1 1 1]]
```