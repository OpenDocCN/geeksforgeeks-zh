# Python sympy.Matrix.col_del() 方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-matrix_col_del-method/](https://www.geeksforgeeks.org/python-sympy-matrix_col_del-method/)

借助 `sympy.Matrix.col_del()` 方法，我们可以删除矩阵的列。

## 语法

`sympy.Matrix().col_del()`

## 返回

返回新矩阵。

### 示例 #1

在给定的示例中，我们可以看到 `sympy.Matrix.col_del()` 方法用于删除矩阵的列并返回新的矩阵。

```py
# Import all the methods from sympy
from sympy import *

# use the col_del() method for matrix
gfg_val = Matrix([[1, 2], [2, 1]]).col_del(1)

print(gfg_val)
```

**输出:**

> `Matrix([[1], [2]])`

### 示例 2

```py
from sympy import *

# use the col_del() method for matrix
gfg_val = Matrix([[1, 2], [2, 3], [23, 45]]).col_del(1)

print(gfg_val)
```

**输出:**

> `Matrix([[1], [2], [23]])`