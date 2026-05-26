# Python 中的 SymPy | Permutation.list()

> 原文: [https://www.geeksforgeeks.org/sympy-permutation-list-in-python/](https://www.geeksforgeeks.org/sympy-permutation-list-in-python/)

## 函数介绍

`Permutation.list()` 是一个 SymPy Python 库函数，它将置换作为显式列表返回。如果大小小于置换中的最大元素，可能会修剪不动的元素。

## 语法与返回值

> **语法:** `sympy.combinatorics.permutations.Permutation.list()`
>
> **返回:** 置换为显式列表

## 代码示例 1: list() 示例

```py
# Python code explaining
# SymPy.Permutation.list()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.list() method

# creating Permutation
a = Permutation([[2, 0], [3, 1]])

b = Permutation([1, 3, 5, 4, 2, 0])

print ("Permutation a - list form : ", a.list())
print ("Permutation b - list form : ", b.list())
```

**输出:**

> Permutation a – list form: [2, 3, 0, 1]
> Permutation b – list form: [1, 3, 5, 4, 2, 0]

## 代码示例 2: list() 示例 – 2D 置换

```py
# Python code explaining
# SymPy.Permutation.list()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.list() method

# creating Permutation
a = Permutation([[2, 4, 0], 
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - list form : ", a.list())
```

**输出:**

> Permutation a – list form: [3, 2, 4, 5, 0, 6, 1]