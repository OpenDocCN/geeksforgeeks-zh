# Python sympy.ones() 方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-ones-method/](https://www.geeksforgeeks.org/python-sympy-ones-method/)

借助 `sympy.ones()` 方法，我们可以创建一个维度为 `n x m` 的矩阵，并使用 `sympy.ones()` 方法填充。

## 语法
`sympy.ones()`

## 返回值
返回一个全为 1 的矩阵。

## 示例 #1
在这个示例中，我们可以看到，通过使用 `sympy.ones()` 方法，我们能够创建维度 `n x n` 全部填充为 1 的矩阵，其中 `n x m` 将作为参数传递。

```py
# import sympy
from sympy import *

# Use sympy.ones() method
mat = ones(3, 4)

print(mat)
```

**输出:**

> 矩阵([
> [1，1，1，1]，
> [1，1，1，1]，
> [1，1，1，1]])

## 示例 2

```py
# import sympy
from sympy import *

# Use sympy.ones() method
mat = ones(3, 2)

print(mat)
```

**输出:**

> 矩阵([
> [1，1]，
> [1，1]，
> [1，1]])