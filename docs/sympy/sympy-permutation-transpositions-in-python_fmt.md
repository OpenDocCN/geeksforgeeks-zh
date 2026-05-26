# Python 中的 SymPy | Permutation.transpositions()

> 原文: [https://www.geeksforgeeks.org/sympy-permutation-transpositions-in-python/](https://www.geeksforgeeks.org/sympy-permutation-transpositions-in-python/)

`Permutation.transpositions()` 是一个 sympy Python 库函数，它返回分解成置换列表的置换。将置换表示为置换的乘积总是可能的。

> **语法:** `Permutation.transpositions()`
> **返回:** 置换分解成置换列表

## 代码#1: `transpositions()` 示例

```py
# Python code explaining
# SymPy.Permutation.transpositions()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from
# sympy.combinatorics.permutations.Permutation.transpositions() method

# creating Permutation
a = Permutation([[2, 0], [3, 1]])

b = Permutation([1, 3, 5, 4, 2, 0])

print ("Permutation a - transpositions form : ", a.transpositions())
print ("Permutation b - transpositions form : ", b.transpositions())
```

**输出:**

> 置换 a – 置换形式: `[(0, 2), (1, 3)]`
> 置换 b – 置换形式: `[(0, 5), (0, 2), (0, 4), (0, 3), (0, 1)]`

## 代码#2: `transpositions()` 示例

```py
# Python code explaining
# SymPy.Permutation.transpositions()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from
# sympy.combinatorics.permutations.Permutation.transpositions() method

# creating Permutation
a = Permutation([[2, 4, 0],
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - transpositions form : ", a.transpositions())
```

**输出:**

> 置换 a – 置换形式: `[(0, 4), (0, 2), (0, 1), (0, 6), (0, 5), (0, 3)]`