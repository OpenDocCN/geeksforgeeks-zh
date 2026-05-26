# SymPy Matrix.eigenvects() 方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-matrix-eigenvects-method/](https://www.geeksforgeeks.org/python-sympy-matrix-eigenvects-method/)

借助 `SymPy` 库的 `Matrix.eigenvects()` 方法，我们可以找到一个矩阵的[特征向量](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)。`eigenvects()` 方法返回形式为 `(特征值: 代数重数, [特征向量])` 的元组列表。

### 语法
`Matrix.eigenvects()`

### 返回
返回以下形式的元组列表 `(特征值: 代数重数, [特征向量])`。

## 示例 #1

```py
# import sympy
from sympy import *
M = Matrix([[3, -2,  4, -2],
            [5,  3, -3, -2],
            [5, -2,  2, -2],
            [5, -2, -3,  3]])

print("Matrix : {} ".format(M))

# Use sympy.eigenvects() method
M_eigenvects = M.eigenvects()

print("Eigenvects of a matrix : {}".format(M_eigenvects))
```

**输出:**

> 矩阵: Matrix([[3, -2, 4, -2], [5, 3, -3, -2], [5, -2, 2, -2], [5, -2, -3, 3]])
> 矩阵的特征向量: [(-2, 1, [Matrix([
> [0],
> [1],
> [1],
> [1]])]), (3, 1, [Matrix([
> [1],
> [1],
> [1],
> [2]])])]

## 示例 2

```py
# import sympy
from sympy import *
M = Matrix([[1, -3, 3], [3, -5, 3], [6, -6, 4]])
print("Matrix : {} ".format(M))

# Use sympy.eigenvects() method
M_eigenvects = M.eigenvects()

print("Eigenvects of a matrix : {}".format(M_eigenvects))
```

**输出:**

> 矩阵: Matrix([[1, -3, 3], [3, -5, 3], [6, -6, 4]])
> 矩阵的本征向量: [(-2, 2, [Matrix([
> [1],
> [1],
> [0]]), Matrix([
> [-1],
> [ 0],
> [ 1]])]), (4, 1, [Matrix([
> [1/2],
> [1/2],
> [  1]])])]