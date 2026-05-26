# Python | sympy.Matrix.row_del()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-matrix-row_del-method/](https://www.geeksforgeeks.org/python-sympy-matrix-row_del-method/)

借助`sympy.Matrix.row_del()`方法，我们可以删除矩阵的行。

## 语法与返回值

> **语法:** `sympy.Matrix().row_del()`
> **返回:** 返回新矩阵。

## 示例 #1

在给定的示例中，我们可以看到`sympy.Matrix.row_del()`方法用于删除矩阵的行并返回一个新矩阵。

```py
# Import all the methods from sympy
from sympy import *

# use the row_del() method for matrix
gfg_val = Matrix([[1, 2], [2, 1]]).col_row(1)

print(gfg_val)
```

**输出:**

> `Matrix([1, 2])`

## 示例 #2

```py
from sympy import *

# use the row_del() method for matrix
gfg_val = Matrix([[1, 2], [2, 3], [23, 45]]).row_del(0)

print(gfg_val)
```

**输出:**

> `Matrix([[2, 3], [23, 45]])`