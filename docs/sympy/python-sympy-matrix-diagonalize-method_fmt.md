# Python SymPy | Matrix.diagonalize()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-matrix-diagonalize-method/](https://www.geeksforgeeks.org/python-sympy-matrix-diagonalize-method/)

借助`Matrix().diagonalize()`方法，我们可以[对角化](https://en.wikipedia.org/wiki/Diagonalizable_matrix)一个矩阵。`diagonalize()`返回一个元组`(P, D)`，其中`D`是对角的，且满足`M = PDP^{-1}`。

> **语法:** `Matrix().diagonalize()`
>
> **返回:** 返回矩阵的元组，其中第二个元素代表矩阵的对角线。

## 示例 #1

```py
# import sympy
from sympy import *
M = Matrix([[3, -2,  4, -2],
            [5,  3, -3, -2],
            [5, -2,  2, -2],
            [5, -2, -3,  3]])

print("Matrix : {} ".format(M))

# Use sympy.diagonalize() method
P, D = M.diagonalize()

print("Diagonal of a matrix : {}".format(D))
```

**输出:**

> 矩阵: Matrix([[3, -2, 4, -2], [5, 3, -3, -2], [5, -2, 2, -2], [5, -2, -3, 3]])
> 矩阵的对角线: Matrix([[-2, 0, 0, 0], [0, 3, 0, 0], [0, 0, 5, 0], [0, 0, 0, 5]])

## 示例 2

```py
# import sympy
from sympy import *
M = Matrix([[1, -3, 3], [3, -5, 3], [6, -6, 4]])
print("Matrix : {} ".format(M))

# Use sympy.diagonalize() method
P, D = M.diagonalize()

print("Diagonal of a matrix : {}".format(D))
```

**输出:**

> 矩阵: Matrix([[1, -3, 3], [3, -5, 3], [6, -6, 4]])
> 矩阵的对角线: Matrix([[-2, 0, 0], [0, -2, 0], [0, 0, 4]])