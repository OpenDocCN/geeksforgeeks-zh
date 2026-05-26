# Python 中的 SymPy | `Polyhedron.array_form()`

> 原文: [https://www.geeksforgeeks.org/sympy-polyhedron-array_form-in-python/](https://www.geeksforgeeks.org/sympy-polyhedron-array_form-in-python/)

`Polyhedron.array_form()` 是一个 sympy Python 库函数，返回多面体的角的索引。

> **语法:**
> `sympy.combinatorics.polyhedron.Polyhedron.array_form()`
>
> **返回:**
> 多面体角的指数

## 代码#1 : `array_form()` 示例–四面体

```py
# Python code explaining
# SymPy.Polyhedron.array_form()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.polyhedron import tetrahedron, octahedron

# Using from
# sympy.combinatorics.polyhedron.Polyhedron.array_form()

# Creating Polyhedron
a = tetrahedron.copy()

print ("Polyhedron - array_form form : ", a.array_form)

a.rotate(0)
print ("\nPolyhedron - array_form form : ", a.array_form)
```

**输出:**

> Polyhedron - array_form form : [0, 1, 2, 3]
>
> Polyhedron - array_form form : [0, 2, 3, 1]

## 代码#2 : `array_form()` 示例–八面体

```py
# Python code explaining
# SymPy.Polyhedron.array_form()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.polyhedron import tetrahedron, octahedron

# Using from
# sympy.combinatorics.polyhedron.Polyhedron.array_form()

# Creating Polyhedron
a = octahedron.copy()

print ("Polyhedron - array_form form : ", a.array_form)

a.rotate(0)
print ("\nPolyhedron - array_form form : ", a.array_form)
```

**输出:**

> Polyhedron - array_form form : [0, 1, 2, 3, 4, 5]
>
> Polyhedron - array_form form : [0, 2, 3, 4, 1, 5]