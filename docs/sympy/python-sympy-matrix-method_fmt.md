# Python | sympy.Matrix()方法

> 原文: `https://www.geeksforgeeks.org/python-sympy-matrix-method/`

借助 `sympy.Matrix()` 方法，我们可以对由 `sympy` 创建的矩阵中不同的行和列进行制作、重排、提取。

> **语法:** `sympy.Matrix()`
> **返回:** 返回一个矩阵。

## 示例 1

在这个示例中，我们可以通过使用 `sympy.Matrix()` 方法，我们可以创建一个矩阵或者可以提取行和列。

### Python 3

```py
# Import all the methods from sympy
from sympy import *

# use the Matrix() method to create a matrix
gfg_val = Matrix([[1, sqrt(2)], [sqrt(2), 1]])

print(gfg_val)
```

**输出:**

> Matrix([[1, sqrt(2)], [sqrt(2), 1]])

## 示例 2

### Python 3

```py
# Import all the methods from sympy
from sympy import *

# use the Matrix() method to create a matrix
gfg_val = Matrix([[1, 2], [2, 3], [3, 4]])

print(gfg_val)
```

**输出:**

> Matrix([[1, 2], [2, 3], [3, 4]])