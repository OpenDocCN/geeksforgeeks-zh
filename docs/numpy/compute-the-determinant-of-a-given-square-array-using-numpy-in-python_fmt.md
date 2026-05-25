# 使用 Python 中的 NumPy 计算给定方阵的行列式

> 原文: [https://www.geeksforgeeks.org/compute-the-determinant-of-a-given-square-array-using-numpy-in-python/](https://www.geeksforgeeks.org/compute-the-determinant-of-a-given-square-array-using-numpy-in-python/)

在 Python 中，使用 NumPy 包可以很容易地计算出方阵的行列式。该软件包用于对一维和多维数组进行数学计算。`numpy.linalg` 是用于线性代数的 numpy 包的重要模块。

我们可以利用 `numpy.linalg` 模块的 `det()` 功能求出方阵的行列式。

> **语法**
> `numpy.linalg.det(array)`
>
> **参数:**
>
> `array(…，M，M) array_like`: 输入要计算行列式的数组。
>
> **返回:**
>
> `det(…) array_like`: 数组的行列式。

## 示例 1：2x2 矩阵的行列式

```python
# Importing libraries
import numpy as np
from numpy import linalg

# Creating a 2X2 matrix
matrix = np.array([[1, 0], [3, 6]])
print("Original 2-D matrix")
print(matrix)

# Output
print("Determinant of the 2-D matrix:")
print(np.linalg.det(matrix))
```

**输出:**

```python
Original 2-D matrix
[[1 0]
 [3 6]]
Determinant of the 2-D matrix:
6.0
```

## 示例 2：3x3 矩阵的行列式

```python
# Importing libraries
import numpy as np
from numpy import linalg

# Creating a 3X3 matrix
matrix = np.array([[1, 0, 1], [1, 2, 0], [4, 6, 2]])
print("Original 3-D matrix")
print(matrix)

# Output
print("Determinant of the 3-D matrix:")
print(np.linalg.det(matrix))
```

**输出:**

```python
Original 3-D matrix
[[1 0 1]
 [1 2 0]
 [4 6 2]]
Determinant of the 3-D matrix:
2.0
```

## 示例 3：4x4 矩阵的行列式

```python
# Importing libraries
import numpy as np
from numpy import linalg

# Creating a 4X4 matrix
matrix = np.array([[1, 0, 1, 8], [1, 2, 0, 3], [4, 6, 2, 6], [0, 3, 6, 4]])
print("Original 4-D matrix")
print(matrix)

# Output
print("Determinant of the 4-D matrix:")
print(np.linalg.det(matrix))
```

**输出:**

```python
Original 4-D matrix
[[1 0 1 8]
 [1 2 0 3]
 [4 6 2 6]
 [0 3 6 4]]
Determinant of the 4-D matrix:
188.0
```