# Python 中的代数矩阵模块

> 原文：[https://www.geeksforgeeks.org/algebraonmatrix-module-in-python/](https://www.geeksforgeeks.org/algebraonmatrix-module-in-python/)

`代数矩阵`模块是 Python 库，帮助你执行基本矩阵代数，如两个矩阵的加法、两个矩阵的减法、两个矩阵的乘法、矩阵的转置。

### 安装库

这个模块没有内置 Python。你需要从外部安装它。要安装此模块，请在终端中键入以下命令。

```py
pip install AlgebraOnMatrix
```

### 代数矩阵的函数

`矩阵`：它会把我们的二维数组转换成矩阵。

**示例：**

```py
# Importing Matrix function
# From AlgebraOnMatrix Library
from AlgebraOnMatrix import Matrix

arr =[[1, 2, 3], [4, 5, 6, ], [7, 8, 9]]

# Now we will transform our 2d array
# into the matrix and make an object
# of it
a = Matrix(arr)
```

### 矩阵运算

*   **矩阵加法：** 在这里，我们将矩阵 `b` 与矩阵 `a` 相加，其中矩阵 `b` 以二维数组形式给出。这通过函数 `Matrix.addition(a, b)` 完成，其中 `a` 是我们创建的对象，`b` 是二维数组。
    **示例：**

```py
# Importing Matrix function
# From AlgebraOnMatrix Library
from AlgebraOnMatrix import Matrix

arr =[[1, 2, 3], [4, 5, 6, ], [7, 8, 9]]

# Now we will transform our 2d array
# into matrix and make an object of it
a = Matrix(arr)

b =[[1, 2, 3], [4, 5, 6, ], [7, 8, 9]]

ans = Matrix.addition(a, b)
print(ans)
```

**输出：**

```py
[[2, 4, 6], [8, 10, 12], [14, 16, 18]]
```

*   **矩阵减法：** 在这里，我们将从矩阵 `a` 中减去矩阵 `b`，其中矩阵 `b` 以二维数组形式给出。这通过函数 `Matrix.subtraction(a, b)` 完成，其中 `a` 是我们创建的对象，`b` 是二维数组。
    **示例：**

```py
# Importing Matrix function
# From AlgebraOnMatrix Library
from AlgebraOnMatrix import Matrix

arr =[[1, 2, 3], [4, 5, 6, ], [7, 8, 9]]

# Now we will transform our 2d array
# into matrix and make an object of it
a = Matrix(arr)

b =[[1, 2, 3], [4, 5, 6, ], [7, 8, 9]]

ans = Matrix.subtraction(a, b)
print(ans)
```

**输出：**

```py
[[0, 0, 0], [0, 0, 0], [0, 0, 0]]
```

*   **矩阵乘法：** 在这里，我们将矩阵 `b` 与矩阵 `a` 相乘，其中矩阵 `b` 以二维数组形式给出。这通过函数 `Matrix.multiplication(a, b)` 完成，其中 `a` 是我们创建的对象，`b` 是二维数组。
    **示例：**

```py
# Importing Matrix function
# From AlgebraOnMatrix Library
from AlgebraOnMatrix import Matrix

arr =[[1, 2, 3], [4, 5, 6, ], [7, 8, 9]]

# Now we will transform our 2d array
# into matrix and make an object of it
a = Matrix(arr)

b =[[1, 2, 3], [4, 5, 6, ], [7, 8, 9]]

ans = Matrix.multiplication(a, b)
print(ans)
```

**输出：**

```py
[[30, 36, 42], [66, 81, 96], [102, 126, 150]]
```

*   **矩阵转置：** 在这里，我们将对矩阵 `a` 进行转置。这通过函数 `Matrix.transpose(a)` 完成，其中 `a` 是我们创建的对象。
    **示例：**

```py
# Importing Matrix function
# From AlgebraOnMatrix Library
from AlgebraOnMatrix import Matrix

arr =[[1, 2, 3], [4, 5, 6, ], [7, 8, 9]]

# Now we will transform our 2d array
# into matrix and make an object of it
a = Matrix(arr)

ans = Matrix.transpose(a)
print(ans)
```

**输出：**

```py
[[1, 4, 7], [2, 5, 8], [3, 6, 9]]
```