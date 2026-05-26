# `Prufer.size()` in SymPy

> 原文: [https://www.geeksforgeeks.org/sympy-prufer-size-in-python/](https://www.geeksforgeeks.org/sympy-prufer-size-in-python/)

`Prufer.size()` 是一个 `sympy` Python 库函数，返回 Prufer 序列的大小。

> **语法:**
> `sympy.combinatorics.prufer.Prufer.size()`
>
> **返回:**
> Prufer 序列的大小

## 代码 #1: `size()` 示例

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
print ("Prufer a size : ", a.size)
```

**输出:**

> Prufer a size: 125

## 代码 #2: `size()` 示例

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
print ("Prufer b size : ", b.size)
```

**输出:**

> Prufer b size: 262144