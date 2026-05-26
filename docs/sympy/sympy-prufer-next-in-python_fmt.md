# Python 中的 SymPy | Prufer.next()

> 原文: [https://www.geeksforgeeks.org/sympy-prufer-next-in-python/](https://www.geeksforgeeks.org/sympy-prufer-next-in-python/)

`Prufer.next()` 是一个 sympy Python 库函数，它返回的 Prufer 序列是当前序列的增量。

### 语法:
`sympy.combinatorics.prufer.Prufer.next()`

### 返回:
超出当前增量的普鲁弗序列

### 代码#1: `next()` 示例

```py
# Python code explaining
# SymPy.Prufer.next()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.prufer import Prufer

# Using from 
# sympy.combinatorics.prufer.Prufer.next()

# Creating Prufer
a = Prufer([1, 2, 3], [2, 4, 5])

# next value
print ("Prufer a next : ", a.next(1))
```

### 输出:
> Prufer a next: Prufer([1, 2, 4])

### 代码#2: `next()` 示例

```py
# Python code explaining
# SymPy.Prufer.next()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.prufer import Prufer

# Using from 
# sympy.combinatorics.prufer.Prufer.next()

# Creating Prufer
b = Prufer([1, 2, 3, 2, 4, 5], [6, 7], [8])

# next value
print ("Prufer b next : ", b.next(1))
```

### 输出:
> Prufer b next: Prufer([1, 2, 3, 2, 4, 6])