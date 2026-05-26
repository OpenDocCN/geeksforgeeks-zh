# Python 中的 SymPy | Polyhedron.pgroup()

> 原文: [https://www.geeksforgeeks.org/sympy-polyhedron-pgroup-in-python/](https://www.geeksforgeeks.org/sympy-polyhedron-pgroup-in-python/)

`Polyhedron.pgroup()` 是一个 sympy Python 库函数，返回多面体的排列。

## 语法

`combinatorics.polyhedron.Polyhedron.pgroup()`

## 返回

多面体的排列。

## 代码#1 : pgroup()示例–四面体

```py
# Python code explaining
# SymPy.Polyhedron.pgroup()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.polyhedron import tetrahedron, octahedron

# Using from 
# sympy.combinatorics.polyhedron.Polyhedron.pgroup()

# Creating Polyhedron
a = tetrahedron.copy()

print ("Polyhedron - pgroup form : ", a.pgroup)

a.rotate(0)
print ("\nPolyhedron - pgroup form : ", a.pgroup)
```

**输出:**

> Polyhedron - pgroup form : PermutationGroup([
> (1 2 3),
> (3)(0 1 2),
> (0 3 2),
> (0 3 1),
> (0 1)(2 3),
> (0 2)(1 3),
> (0 3)(1 2)])
>
> Polyhedron - pgroup form : PermutationGroup([
> (1 2 3),
> (3)(0 1 2),
> (0 3 2),
> (0 3 1),
> (0 1)(2 3),
> (0 2)(1 3),
> (0 3)(1 2)])

## 代码#2 : pgroup()示例–八面体

```py
# Python code explaining
# SymPy.Polyhedron.pgroup()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.polyhedron import tetrahedron, octahedron

# Using from 
# sympy.combinatorics.polyhedron.Polyhedron.pgroup()

# Creating Polyhedron
a = octahedron.copy()

print ("Polyhedron - pgroup form : ", a.pgroup)

a.rotate(0)
print ("\nPolyhedron - pgroup form : ", a.pgroup)
```

**输出:**

> Polyhedron - pgroup form : PermutationGroup([
> (5)(1 2 3 4),
> (0 4 5 2),
> (0 1 5 3),
> (0 1)(2 4)(3 5),
> (0 2)(1 3)(4 5),
> (0 3)(1 5)(2 4),
> (0 4)(1 3)(2 5),
> (0 5)(1 4)(2 3),
> (0 5)(1 2)(3 4),
> (0
>
> Polyhedron - pgroup form : PermutationGroup([
> (5)(1 2 3 4),
> (0 4 5 2),
> (0 1 5 3),
> (0 1)(2 4)(3 5),
> (0 2)(1 3)(4 5),
> (0 3)(1 5)(2 4),
> (0 4)(1 3)(2 5),
> (0 5)(1 4)(2 3),
> (0 5)(1 2)(3 4),
> (0