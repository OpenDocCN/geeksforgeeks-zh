# SymPy Prufer.unrank() 函数详解

## 概述

`Prufer.unrank()` 是 SymPy Python 库中的一个函数，用于返回未链接的 Prufer 序列。

> 原文: [https://www.geeksforgeeks.org/sympy-prufer-unrank-in-python/](https://www.geeksforgeeks.org/sympy-prufer-unrank-in-python/)

**语法:**
`sympy.combinatorics.prufer.Prufer.unrank()`

**返回:**
解开普鲁弗序列

## 代码示例 1

```py
# Python code explaining
# SymPy.Prufer.unrank()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.prufer import Prufer

# Using from
# sympy.combinatorics.prufer.Prufer.unrank()

# Creating Prufer
a = Prufer([1, 2, 3], [2, 4, 5])

# unrank value
# rank = 2
# n = 5
print ("Prufer a unrank : ", a.unrank(2, 5))
```

**输出:**

> Prufer a unrank: [1, 2, 5]

## 代码示例 2

```py
# Python code explaining
# SymPy.Prufer.unrank()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.prufer import Prufer

# Using from
# sympy.combinatorics.prufer.Prufer.unrank()

# Creating Prufer
b = Prufer([1, 2, 3, 2, 4, 5], [6, 7], [8])

# unrank value
# rank = 2
# n = 5
print ("Prufer b unrank : ", b.unrank(2, 5))
```

**输出:**

> Prufer b unrank: Prufer([0, 0, 2])