# Python中的SymPy：`Subset.next_lexicographic()`

> 原文：[https://www.geeksforgeeks.org/sympy-subset-next_lexicographic-in-python/](https://www.geeksforgeeks.org/sympy-subset-next_lexicographic-in-python/)

`Subset.next_lexicographic()` 是一个 SymPy Python 库函数，用于返回下一个字典序子集。

> **语法：**
> `sympy.combinatorics.subset.Subset.next_lexicographic()`
>
> **返回：**
> 下一个字典序子集

**代码# 1：`next_lexicographic()` 示例**

```py
# Python code explaining
# SymPy.Subset.next_lexicographic()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.subsets import Subset

# Using from
# sympy.combinatorics.subset.Subset.next_lexicographic()

# Creating Subset
a = Subset(['c', 'd'], ['geek', 'for', 'c', 'd'])

# next_lexicographic value
print ("Subset a next_lexicographic : ", a.next_lexicographic().subset)
```

**输出：**

> 子集 a next_lexicographic 顺序：`['d']`

**代码# 2：`next_lexicographic()` 示例**

```py
# Python code explaining
# SymPy.Subset.next_lexicographic()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.subsets import Subset

# Using from
# sympy.combinatorics.subset.Subset.next_lexicographic()

# Creating Subset
a = Subset(['k', 'a'], ['23', 'k', 'a'])

# next_lexicographic value
print ("Subset a next_lexicographic : ", a.next_lexicographic().subset)
```

**输出：**

> 子集 a next_lexicographic 顺序：`['a']`