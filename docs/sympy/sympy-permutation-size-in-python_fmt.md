# Python 中的 SymPy | Permutation.size()

> 原文: [https://www.geeksforgeeks.org/sympy-permutation-size-in-python/](https://www.geeksforgeeks.org/sympy-permutation-size-in-python/)

`Permutation.size()` 是一个 SymPy Python 库函数，返回排列中的元素个数。

> **语法:** `sympy.combinatorics.permutations.Permutation.size()`
>
> **返回:** 排列中的元素个数。

## 代码#1: `size()` 示例

```py
# Python code explaining
# SymPy.Permutation.size()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from
# sympy.combinatorics.permutations.Permutation.size() method

# creating Permutation
a = Permutation([[2, 0], [3, 1]])

b = Permutation([1, 3, 5, 4, 2, 0])

print ("Permutation a - size form : ", a.size)
print ("Permutation b - size form : ", b.size)
```

**输出:**

> Permutation a - size form : 4
> Permutation b - size form : 6

## 代码#2: `size()` 示例

```py
# Python code explaining
# SymPy.Permutation.size()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from
# sympy.combinatorics.permutations.Permutation.size() method

# creating Permutation
a = Permutation([[2, 4, 0],
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - size form : ", a.size)
```

**输出:**

> Permutation a - size form : 7