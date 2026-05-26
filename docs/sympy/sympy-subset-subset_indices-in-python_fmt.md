# SymPy中的`Subset.subset_indices()`方法

> 原文: [https://www.geeksforgeeks.org/sympy-subset-subset_indices-in-python/](https://www.geeksforgeeks.org/sympy-subset-subset_indices-in-python/)

`Subset.subset_indices()` 是一个 SymPy Python 库函数，用于返回列表（超集）中子集的索引。

> **语法:**
> `sympy.combinatorics.subsets.Subset.subset_indices()`
>
> **返回:**
> 列表中超集中子集的索引。如果子集的所有元素都不在超集中，则返回空列表。

## 代码示例 1：`subset_indices()` 示例

```py
# Python code explaining
# SymPy.Subset.subset_indices()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.subsets import Subset

# Using from
# sympy.combinatorics.subset.Subsets.subset_indices()

# superset
super_set = [4, 3, 2, 7]

# Creating Subset
a = Subset.subset_indices((['geek', 'for', 'c', 'd']), super_set)

# subset_indices value
print ("Subset a subset_indices : ", a)
```

**输出:**

> Subset a subset_indices : []

## 代码示例 2：`subset_indices()` 示例

```py
# Python code explaining
# SymPy.Subset.subset_indices()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.subsets import Subset

# Using from
# sympy.combinatorics.subset.Subsets.subset_indices()

# superset
super_set = [4, 3, 2, 7]

# Creating Subset
a = Subset.subset_indices(([2, 3, 4]), super_set)

# subset_indices value
print ("Subset a subset_indices : ", a)
```

**输出:**

> Subset a subset_indices : [2, 1, 0]