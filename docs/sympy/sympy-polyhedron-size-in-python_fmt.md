# Python 中的 SymPy | `Polyhedron.size()`

> 原文: [`https://www.geeksforgeeks.org/sympy-polyhedron-size-in-python/`](https://www.geeksforgeeks.org/sympy-polyhedron-size-in-python/)

`Polyhedron.size()` 是一个 `sympy` Python 库函数，返回多面体的角个数的计数。

> **语法:** `sympy.combinatorics.polyhedron.Polyhedron.size()`
>
> **返回:** 计算多面体的角数

**代码#1: `size()` 示例–四面体**

```py
# Python code explaining
# SymPy.Polyhedron.size()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.polyhedron import tetrahedron, octahedron

# Using from
# sympy.combinatorics.polyhedron.Polyhedron.size()

# Creating Polyhedron
a = tetrahedron.copy()

print ("Polyhedron - size form : ", a.size)

a.rotate(0)
print ("\nPolyhedron - size form : ", a.size)
```

**输出:**

> Polyhedron - size form : 4
>
> Polyhedron - size form : 4

**代码#2: `size()` 示例–八面体**

```py
# Python code explaining
# SymPy.Polyhedron.size()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.polyhedron import tetrahedron, octahedron

# Using from
# sympy.combinatorics.polyhedron.Polyhedron.size()

# Creating Polyhedron
a = octahedron.copy()

print ("Polyhedron - size form : ", a.size)

a.rotate(0)
print ("\nPolyhedron - size form : ", a.size)
```

**输出:**

> Polyhedron - size form : 6
>
> Polyhedron - size form : 6