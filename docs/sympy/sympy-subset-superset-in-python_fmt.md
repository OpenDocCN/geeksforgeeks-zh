# Python 中的 SymPy Subset.superset()

> 原文: [https://www.geeksforgeeks.org/sympy-subset-superset-in-python/](https://www.geeksforgeeks.org/sympy-subset-superset-in-python/)

`subset.superset()` 是一个 SymPy Python 库函数，返回子集的超集。

## 语法

`sympy.combinatorics.subset.Subset.superset()`

## 返回

子集的超集。

## 代码示例 1：superset() 示例

```py
# Python code explaining
# SymPy.Subset.superset()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.subsets import Subset

# Using from 
# sympy.combinatorics.subset.Subsets.superset()

# Creating Subset
a = Subset(['c', 'd'], ['geek', 'for', 'c', 'd'])

# superset value
print ("Subset a superset : ", a.superset)
```

**输出:**

> Subset a superset: ['geek', 'for', 'c', 'd']

## 代码示例 2：superset() 示例

```py
# Python code explaining
# SymPy.Subset.superset()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.subsets import Subset

# Using from 
# sympy.combinatorics.subset.Subsets.superset()

# Creating Subset
a = Subset([2, 3, 4], [1, 2, 3, 4, 5])

# superset value
print ("Subset a superset : ", a.superset)
```

**输出:**

> Subset a superset: [1, 2, 3, 4, 5]