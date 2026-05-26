# Python 中的 SymPy | Polyhedron.edges()

> 原文: [https://www.geeksforgeeks.org/sympy-polyhedron-edges-in-python/](https://www.geeksforgeeks.org/sympy-polyhedron-edges-in-python/)

`Polyhedron.edges()` 是一个返回多面体边缘的 SymPy Python 库函数。

## 语法:
```
combinatorics.polyhedron.Polyhedron.edges()
```

## 返回:
多面体的边。

## 代码#1: edges() 示例 – 四面体

```py
# Python code explaining
# SymPy.Polyhedron.edges()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.polyhedron import tetrahedron, octahedron

# Using from
# sympy.combinatorics.polyhedron.Polyhedron.edges()

# Creating Polyhedron
a = tetrahedron.copy()

print ("Polyhedron - edges form : ", a.edges)

a.rotate(0)
print ("\nPolyhedron - edges form : ", a.edges)
```

**输出:**
> Polyhedron - edges form : {(0, 1), (0, 2), (0, 3), (1, 2), (1, 3), (2, 3)}
> Polyhedron - edges form : {(0, 1), (0, 2), (0, 3), (1, 2), (1, 3), (2, 3)}

## 代码#2: edges() 示例 – 八面体

```py
# Python code explaining
# SymPy.Polyhedron.edges()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.polyhedron import tetrahedron, octahedron

# Using from
# sympy.combinatorics.polyhedron.Polyhedron.edges()

# Creating Polyhedron
a = octahedron.copy()

print ("Polyhedron - edges form : ", a.edges)

a.rotate(0)
print ("\nPolyhedron - edges form : ", a.edges)
```

**输出:**
> Polyhedron - edges form : {(0, 1), (0, 2), (0, 3), ..., (3, 4), (3, 5), (4, 5)}
> Polyhedron - edges form : {(0, 1), (0, 2), (0, 3), ..., (3, 4), (3, 5), (4, 5)}