# Python 中的 SymPy 子集.超集大小()

> 原文: [https://www.geeksforgeeks.org/sympy-subset-superset_size-in-python/](https://www.geeksforgeeks.org/sympy-subset-superset_size-in-python/)

`subset.superset_size():superset_size()` 是一个 SymPy Python 库函数，返回超集的大小。

## 语法

```
sympy.combinations.subset.subset.superset_size()
```

## 返回

超集的大小。

## 代码示例 1: `superset_size()` 示例

```py
# Python code explaining
# SymPy.Subset.superset_size()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.subsets import Subset

# Using from
# sympy.combinatorics.subset.Subsets.superset_size()

# Creating Subset
a = Subset(['c', 'd'], ['geek', 'for', 'c', 'd'])

# superset_size value
print ("Subset a superset_size : ", a.superset_size)
```

**输出:**

> 子集 a 超集大小:4

## 代码示例 2: `superset_size()` 示例

```py
# Python code explaining
# SymPy.Subset.superset_size()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.subsets import Subset

# Using from
# sympy.combinatorics.subset.Subsets.superset_size()

# Creating Subset
a = Subset([2, 3, 4], [1, 2, 3, 4, 5])

# superset_size value
print ("Subset a superset_size : ", a.superset_size)
```

**输出:**

> 子集 a 超集大小:5