# SymPy Prufer.edges() in Python

## 概述

> 原文: [https://www.geeksforgeeks.org/sympy-prufer-edges-in-python/](https://www.geeksforgeeks.org/sympy-prufer-edges-in-python/)

`Prufer.edges()` 是一个 SymPy Python 库函数，它返回给定 Prufer 序列对应的树中的节点数和边列表，这些节点由整数标记。

## 语法

```python
sympy.combinatorics.prufer.Prufer.edges()
```

## 返回值

节点数和边列表。

## 代码示例

### 代码 #1: `edges()` 示例

```py
# Python code explaining
# SymPy.Prufer.edges()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.prufer import Prufer

# Using from
# sympy.combinatorics.prufer.Prufer.edges()

# Creating Prufer
a = Prufer.edges([1, 2, 3], [2, 4, 5])

# edge value
print ("Prufer a edges : ", a)
```

**输出:**

Prufer a edges : ([[0, 1], [1, 2], [1, 3], [3, 4]], 5)

### 代码 #2: `edges()` 示例

```py
# Python code explaining
# SymPy.Prufer.edges()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.prufer import Prufer

# Using from
# sympy.combinatorics.prufer.Prufer.edges()

# Creating Prufer
b = Prufer.edges([1, 2, 3, 2, 4, 5], [6, 7], [8])

# edge value

print ("Prufer b edges : ", b)
```

**输出:**

Prufer b edges : ([[0, 1], [1, 2], [1, 3], [3, 4], [5, 6], [5, 7]], 8)