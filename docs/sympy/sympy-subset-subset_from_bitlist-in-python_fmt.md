# Python 中的 SymPy | subset.subset_from_bitlist()

> 原文: [https://www.geeksforgeeks.org/sympy-subset-subset_from_bitlist-in-python/](https://www.geeksforgeeks.org/sympy-subset-subset_from_bitlist-in-python/)

`subset.subset_from_bitlist()` 是一个 SymPy Python 库函数，返回位列表定义的子集。

## 语法
`sympy.combinatorics.subsets.Subset.subset_from_bitlist()`

## 返回
位列表定义的子集

**代码#1 : `subset_from_bitlist()` 示例**

```py
# Python code explaining
# SymPy.Subset.subset_from_bitlist()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.subsets import Subset

# Using from
# sympy.combinatorics.subsets.Subset.subset_from_bitlist()

# Creating Subset
a = Subset.subset_from_bitlist( (['geek', 'for', 'c', 'd']), '0101')

# subset_from_bitlist value
print ("Subset a subset_from_bitlist : ", a.subset)
```

**输出:**

> subset a subset_from_bitlist: ['for', 'd']

**代码#2 : `subset_from_bitlist()` 示例**

```py
# Python code explaining
# SymPy.Subset.subset_from_bitlist()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.subsets import Subset

# Using from
# sympy.combinatorics.subsets.Subset.subset_from_bitlist()

# Creating Subset
a = Subset.subset_from_bitlist(([2, 3, 3, 4]), '1011')

# subset_from_bitlist value
print ("Subset a subset_from_bitlist : ", a.subset)
```

**输出:**

> 子集 a subset_from_bitlist: [2, 3, 4]