# SymPy Prufer.rank() in Python

> 原文: [https://www.geeksforgeeks.org/sympy-prufer-rank-in-python/](https://www.geeksforgeeks.org/sympy-prufer-rank-in-python/)

`Prufer.rank()` 是一个 SymPy Python 库函数，返回 Prufer 序列的秩。

**语法:**
`sympy.combinatorics.prufer.Prufer.rank()`

**返回:**
Prufer 序列的秩。

**代码 #1: `rank()` 示例**

```py
# Python code explaining
# SymPy.Prufer.rank()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.prufer import Prufer

# Using from
# sympy.combinatorics.prufer.Prufer.rank()

# Creating Prufer
a = Prufer([1, 2, 3], [2, 4, 5])

# rank value
print ("Prufer a rank : ", a.rank)
```

**输出:**

> Prufer a rank : 38

**代码 #2: `rank()` 示例**

```py
# Python code explaining
# SymPy.Prufer.rank()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.prufer import Prufer

# Using from
# sympy.combinatorics.prufer.Prufer.rank()

# Creating Prufer
b = Prufer([1, 2, 3, 2, 4, 5], [6, 7], [8])

# rank value
print ("Prufer b rank : ", b.rank)
```

**输出:**

> Prufer b rank : 42661