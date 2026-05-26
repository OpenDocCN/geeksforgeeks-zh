# Python 中的 SymPy | Polyhedron.reset()

> 原文: [https://www.geeksforgeeks.org/sympy-polyhedron-reset-in-python/](https://www.geeksforgeeks.org/sympy-polyhedron-reset-in-python/)

`Polyhedron.reset()` 是一个 sympy Python 库函数，它将角点返回到多面体的原始位置。

## 语法
`sympy.combinatorics.polyhedron.Polyhedron.reset()`

## 返回
角到多面体的原始位置

### 代码#1: `reset()` 示例–四面体

```py
# Python code explaining
# SymPy.Polyhedron.reset()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.polyhedron import tetrahedron, octahedron

# Using from 
# sympy.combinatorics.polyhedron.Polyhedron.reset()

# Creating Polyhedron
a = tetrahedron.copy()

print ("Polyhedron - reset form : ", a.reset)

a.rotate(0)
print ("\nPolyhedron - reset form : ", a.reset)
```

**输出:**

> Polyhedron - reset form:
>
> Polyhedron - reset form:

### 代码#2: `reset()` 示例–八面体

```py
# Python code explaining
# SymPy.Polyhedron.reset()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.polyhedron import tetrahedron, octahedron

# Using from 
# sympy.combinatorics.polyhedron.Polyhedron.reset()

# Creating Polyhedron
a = octahedron.copy()

print ("Polyhedron - reset form : ", a.reset)

a.rotate(0)
print ("\nPolyhedron - reset form : ", a.reset)
```

**输出:**

> Polyhedron - reset form:
>
> Polyhedron - reset form: