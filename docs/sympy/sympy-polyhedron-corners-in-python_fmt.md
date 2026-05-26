# Python中的SymPy | Polyhedron.corners()

> 原文: [https://www.geeksforgeeks.org/sympy-polyhedron-corners-in-python/](https://www.geeksforgeeks.org/sympy-polyhedron-corners-in-python/)

`Polyhedron.corners()` 是一个返回多面体角的 sympy Python 库函数。

## 语法
```python
combinatorics.Polyhedron.Polyhedron.corners()
```

## 返回
多面体的角

## 代码#1: `corners()` 示例 – 四面体
```python
# Python code explaining
# SymPy.Polyhedron.corners()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.polyhedron import tetrahedron, octahedron

# Using from 
# sympy.combinatorics.polyhedron.Polyhedron.corners()

# Creating Polyhedron
a = tetrahedron.copy()

print ("Polyhedron - corners form : ", a.corners)

a.rotate(0)
print ("\nPolyhedron - corners form : ", a.corners)
```

**输出:**
> Polyhedron - corners form : (0, 1, 2, 3)
> 
> Polyhedron - corners form : (0, 2, 3, 1)

## 代码#2: `corners()` 示例 – 八面体
```python
# Python code explaining
# SymPy.Polyhedron.corners()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.polyhedron import tetrahedron, octahedron

# Using from 
# sympy.combinatorics.polyhedron.Polyhedron.corners()

# Creating Polyhedron
a = octahedron.copy()

print ("Polyhedron - corners form : ", a.corners)

a.rotate(0)
print ("\nPolyhedron - corners form : ", a.corners)
```

**输出:**
> Polyhedron - corners form : (0, 1, 2, 3, 4, 5)
> 
> Polyhedron - corners form : (0, 2, 3, 4, 1, 5)