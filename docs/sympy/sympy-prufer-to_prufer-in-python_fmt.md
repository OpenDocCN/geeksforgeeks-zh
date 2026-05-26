# Prufer.to_Prufer() 在 Python 中

> 原文: [https://www.geeksforgeeks.org/sympy-prufer-to_prufer-in-python/](https://www.geeksforgeeks.org/sympy-prufer-to_prufer-in-python/)

`Prufer.to_Prufer()` 是一个 `sympy` Python 库函数，它返回一个参数树的 Prufer 序列，该序列以边列表的形式给出，`n` 是树中的节点数。

**语法:**
`Prufer.to_Prufer()`

**返回:**
参数树的 Prufer 序列。

## 代码示例 1: `to_prufer()` 示例

```py
# Python code explaining
# SymPy.Prufer.size()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.prufer import Prufer

# Using from
# sympy.combinatorics.prufer.Prufer.size()

# Creating Prufer
a = Prufer([1, 2, 3], [2, 4, 5])

# size value
print ("Prufer a size : ", a.to_prufer([[0, 1], [0, 2], [0, 3]], 4))
```

**输出:**

> Prufer a size : [0, 0]

## 代码示例 2: `to_prufer()` 示例

```py
# Python code explaining
# SymPy.Prufer.size()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.prufer import Prufer

# Using from
# sympy.combinatorics.prufer.Prufer.size()

# Creating Prufer
b = Prufer([1, 2, 3, 2, 4, 5], [6, 7], [8])

# size value
print ("Prufer b size : ", b.to_prufer([[0, 1], [0, 2], [0, 3]], 4))
```

**输出:**

> Prufer b size : [0, 0]