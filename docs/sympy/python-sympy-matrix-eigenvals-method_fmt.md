# Python | `sympy.Matrix.eigenvals()` 方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-matrix-eigenvals-method/](https://www.geeksforgeeks.org/python-sympy-matrix-eigenvals-method/)

借助 `sympy.Matrix.eigenvals()` 方法，我们可以找到矩阵的特征值。

## 语法
> **语法:** `Matrix().eigenvals()`
> **返回:** 返回矩阵的特征值。

## 示例 #1
在给定的例子中，我们可以看到 `eigenvals()` 方法用于求矩阵的特征值。

### Python 3

```py
# Import all the methods from sympy
from sympy import *

# use the eigenvals() method for matrix
gfg_val = Matrix([[1, 2], [2, 1]]).eigenvals()

print(gfg_val)
```

**输出:**

> {3: 1, -1: 1}

## 示例 2

### Python 3

```py
from sympy import *

# use the eigenvals() method for matrix
gfg_val = Matrix([[1, 2], [2, 2]]).eigenvals()

print(gfg_val)
```

**输出:**

> { 3/2–sqrt(17)/2:1, 3/2+sqrt(17)/2:1 }