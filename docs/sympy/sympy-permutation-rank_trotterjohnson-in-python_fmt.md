# Python 中的 SymPy | Permutation.rank_trotterjohnson()

> 原文: [https://www.geeksforgeeks.org/sympy-permutation-rank_trotterjohnson-in-python/](https://www.geeksforgeeks.org/sympy-permutation-rank_trotterjohnson-in-python/)

`Permutation.rank_trotterjohnson()` 是一个 SymPy Python 库函数，返回非字典序排列的 Trotter-Johnson 秩。

> **语法:** `sympy.combinatorics.permutations.Permutation.rank_trotterjohnson()`
>
> **返回:** 字典序 `rank_trotterjohnson` 中的下一个排列

## 代码#1 : `rank_trotterjohnson()` 示例

```py
# Python code explaining
# SymPy.Permutation.rank_trotterjohnson()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from
# sympy.combinatorics.permutations.Permutation.rank_trotterjohnson() method

# creating Permutation
a = Permutation([[2, 0], [3, 1]])

b = Permutation([1, 3, 5, 4, 2, 0])

print ("Permutation a - rank_trotterjohnson form : ", a.rank_trotterjohnson())
print ("Permutation b - rank_trotterjohnson form : ", b.rank_trotterjohnson())
```

**输出:**

> Permutation a – rank_trotterjohnson form: 10
> Permutation b – rank_trotterjohnson form: 555

## 代码#2 : `rank_trotterjohnson()` 示例 – 2D 置换

```py
# Python code explaining
# SymPy.Permutation.rank_trotterjohnson()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from
# sympy.combinatorics.permutations.Permutation.rank_trotterjohnson() method

# creating Permutation
a = Permutation([[2, 4, 0],
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - rank_trotterjohnson form : ", a.rank_trotterjohnson())
```

**输出:**

> Permutation a – rank_trotterjohnson form: 2420