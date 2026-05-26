# Python 中的 SymPy | `Polyhedron.vertices()`

> 原文: `https://www.geeksforgeeks.org/sympy-polyhedron-vertices-in-python/`

`Polyhedron.vertices()` 是一个返回多面体顶点的 SymPy Python 库函数。

> **语法:** `combinatorics.polyhedron.Polyhedron.vertices()`
> 
> **返回:** 多面体的顶点。

## 代码#1: `vertices()` 示例–四面体

```py
# Python code explaining
# SymPy.Polyhedron.vertices()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.polyhedron import tetrahedron, octahedron

# Using from
# sympy.combinatorics.polyhedron.Polyhedron.vertices()

# Creating Polyhedron
a = tetrahedron.copy()

print ("Polyhedron - vertices form : ", a.vertices)

a.rotate(0)
print ("\nPolyhedron - vertices form : ", a.vertices)
```

**输出:**

> Polyhedron - vertices form : (0, 1, 2, 3)
> 
> Polyhedron - vertices form : (0, 2, 3, 1)

## 代码#2: `vertices()` 示例–八面体

```py
# Python code explaining
# SymPy.Polyhedron.vertices()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.polyhedron import tetrahedron, octahedron

# Using from
# sympy.combinatorics.polyhedron.Polyhedron.vertices()

# Creating Polyhedron
a = octahedron.copy()

print ("Polyhedron - vertices form : ", a.vertices)

a.rotate(0)
print ("\nPolyhedron - vertices form : ", a.vertices)
```

**输出:**

> Polyhedron - vertices form : (0, 1, 2, 3, 4, 5)
> 
> Polyhedron - vertices form : (0, 2, 3, 4, 1, 5)