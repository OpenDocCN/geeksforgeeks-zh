# Python 中的 SymPy | Permutation.support()

> 原文: [https://www.geeksforgeeks.org/sympy-permutation-support-in-python/](https://www.geeksforgeeks.org/sympy-permutation-support-in-python/)

`Permutation.support()` 是一个 sympy Python 库函数，返回置换 `P` 中满足 `P[i] != i` 的元素。

> **语法:** `sympy.combinatorics.permutations.Permutation.support()`
>
> **返回:** 置换中的元素 `P`，为哪个 `P[i] != i`。

## 代码#1: `support()` 示例

```py
# Python code explaining
# SymPy.Permutation.support()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.support() method

# creating Permutation
a = Permutation([[2, 0], [3, 1]])

b = Permutation([1, 3, 5, 4, 2, 0])

print ("Permutation a - support form : ", a.support())
print ("Permutation b - support form : ", b.support())
```

**输出:**

> Permutation a – support form: [0, 1, 2, 3]
> Permutation b – support form: [0, 1, 2, 3, 4, 5]

## 代码#2: `support()` 示例

```py
# Python code explaining
# SymPy.Permutation.support()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from
# sympy.combinatorics.permutations.Permutation.support() method

# creating Permutation
a = Permutation([[2, 4, 0],
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - support form : ", a.support())
```

**输出:**

> Permutation a – support form: [0, 1, 2, 3, 4, 5, 6]