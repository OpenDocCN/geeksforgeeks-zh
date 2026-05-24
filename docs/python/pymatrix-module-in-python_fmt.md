# Python 中的 Pymatrix 模块

> 原文:[https://www.geeksforgeeks.org/pymatrix-module-in-python/](https://www.geeksforgeeks.org/pymatrix-module-in-python/)

Pymatrix 是一个轻量级的矩阵库，支持基本的线性代数运算。矩阵中的元素应该是数值型的，以支持基本的代数运算——整型、浮点型、有理型、复数型。

## 实例化矩阵

### 使用矩阵构造器
矩阵可以使用 `pymatrix` 库中 `Matrix` 类的构造器进行初始化。

> **语法:** `Matrix(行, 列, 填充=val(可选))`
> **参数 :**
> **行** – 指定行数
> **列数** – 指定列数
> **填充** – 用该值初始化所有元素。这是一个可选参数，默认填充为 0。

**例:**

```py
import pymatrix

m = pymatrix.Matrix(2, 3, fill = '2')
print(m)
```

**输出:**

```py
2 2 2
2 2 2
```

### 使用列表列表
我们可以使用 `from_list()` 方法将列表列表转换为矩阵，其中每个列表都被视为一行。示例-

```py
import pymatrix

list = [[1, 2, 3], [6, 4, 7], [3, 9, 1]]
m = pymatrix.Matrix.from_list(list)
print(m)
```

**输出:**

```py
1 2 3
6 4 7
3 9 1
```

### 使用字符串
我们可以使用 `from_string()` 方法将字符串转换为矩阵对象。字符串用三重引号括起来，每一行都被视为一行。示例

```py
import pymatrix

string = '''1 2 3
       6 4 7
       3 9 1'''

m = pymatrix.Matrix.from_string(string)
print(m)
```

**输出:**

```py
1 2 3
6 4 7
3 9 1
```

## 矩阵方法
以下是 `pymatrix` 库中提供的一些方法:

*   `identity()` – 创建给定大小的单位矩阵。这将返回 `Matrix` 类的对象。
*   `is_square()` – 检查给定矩阵是否为正方形矩阵。这将返回一个布尔值。
*   `is_invertible()` – 检查给定矩阵是否可逆。这将返回一个布尔值。
*   `inv()` – 如果逆矩阵存在，则返回逆矩阵，否则引发 `MatrixError` 异常。
*   `det()` – 如果是方阵则返回行列式矩阵，否则引发 `MatrixError(“非方阵没有行列式”)` 异常。
*   `rank()` – 返回矩阵的秩，秩为整数类型。
*   `trans()` – 返回矩阵的转置。
*   `adjoint()` – 返回伴随矩阵。

**例:**

```py
# Python program for Matrix methods
from pymatrix import Matrix

# identity matrix of size 2
identity_matrix = Matrix.identity(2)
print('\nIdentity matrix :')
print(identity_matrix)

m = Matrix.from_list([[1,2,1],[2,1,1],[1,1,1]])

print('\nIs a square matrix :')
print(m.is_square())

print('\nIs an invertible matrix :')
print(m.is_invertible())

print('\nInverse :')
print(m.inv())

print('\nDeterminant :')
print(m.det())

print('\nRank :')
print(m.rank())

print('\nTranspose :')
print(m.trans())

print('\nAdjoint :')
print(m.adjoint())
```

**输出:**

```py
Identity matrix :
1 0
0 1

Is a square matrix :
True

Is an invertible matrix :
True

Inverse :
 0.0  1.0 -1.0
 1.0  0.0 -1.0
-1.0 -1.0  3.0

Determinant :
-1.0

Rank :
3

Transpose :
1 2 1
2 1 1
1 1 1

Adjoint :
 0.0 -1.0  1.0
-1.0  0.0  1.0
 1.0  1.0 -3.0
```