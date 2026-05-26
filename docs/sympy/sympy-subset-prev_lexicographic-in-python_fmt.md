# Python 中的 SymPy | subset.prev_lexicographic()

> 原文: [https://www.geeksforgeeks.org/sympy-subset-prev_lexicographic-in-python/](https://www.geeksforgeeks.org/sympy-subset-prev_lexicographic-in-python/)

`subset.prev_lexicographic()` 是一个 SymPy Python 库函数，返回之前的字典序子集。

## 语法

`sympy.combinatorics.subsets.Subset.prev_lexicographic()`

## 返回

之前的字典序有序子集。

## 代码示例 1：prev_lexicographic() 示例

```py
# Python code explaining
# SymPy.Subset.prev_lexicographic()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.subsets import Subset

# Using from 
# sympy.combinatorics.subset.Subset.prev_lexicographic()

# Creating Subset
a = Subset(['c', 'd'], ['geek', 'for', 'c', 'd'])

# prev_lexicographic value
print ("Subset a prev_lexicographic : ", a.prev_lexicographic().subset)
```

**输出：**

> 子集 a prev_词典顺序: ['c']

## 代码示例 2：prev_lexicographic() 示例

```py
# Python code explaining
# SymPy.Subset.prev_lexicographic()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.subsets import Subset

# Using from 
# sympy.combinatorics.subset.Subset.prev_lexicographic()

# Creating Subset
a = Subset([2, 3, 4], [1, 2, 3, 4, 5])

# prev_lexicographic value
print ("Subset a prev_lexicographic : ", a.prev_lexicographic().subset)
```

**输出：**

> 子集 a prev_字典顺序: [2, 3]