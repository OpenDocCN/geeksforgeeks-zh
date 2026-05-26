# Prufer.tree_repr() 在 Python 中的使用

> 原文: [https://www.geeksforgeeks.org/sympy-prufer-tree_repr-in-python/](https://www.geeksforgeeks.org/sympy-prufer-tree_repr-in-python/)

`Prufer.tree_repr()` 是 SymPy Python 库中的一个函数，用于返回 Prufer 序列的树形表示。

**语法:**
`sympy.combinatorics.prufer.Prufer.tree_repr()`

**返回:**
Prufer 序列的树形表示。

## 代码示例 1：`tree_repr()` 基础用法

```python
# Python code explaining
# SymPy.Prufer.tree_repr()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.prufer import Prufer

# Using from
# sympy.combinatorics.prufer.Prufer.tree_repr()

# Creating Prufer
a = Prufer([1, 2, 3], [2, 4, 5])

# tree_repr value
# rank = 2
# n = 5
print("Prufer a tree_repr : ", a.tree_repr())
```

**输出:**

```
Prufer a tree_repr :  [[0, 1], [1, 2], [2, 3], [3, 4]]
```

## 代码示例 2：`tree_repr()` 另一个示例

```python
# Python code explaining
# SymPy.Prufer.tree_repr()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.prufer import Prufer

# Using from
# sympy.combinatorics.prufer.Prufer.tree_repr()

# Creating Prufer
b = Prufer([1, 2, 3, 2, 4, 5], [6, 7], [8])

# tree_repr value
# rank = 2
# n = 5
print("Prufer b tree_repr : ", b.tree_repr())
```

**输出:**

```
Prufer b tree_repr :  [[0, 1], [1, 2], [3, 6], [2, 3], [2, 4], [4, 5], [5, 7]]
```