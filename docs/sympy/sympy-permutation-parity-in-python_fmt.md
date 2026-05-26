# Python 中的 SymPy | Permutation.parity()

> 原文: [https://www.geeksforgeeks.org/sympy-permutation-parity-in-python/](https://www.geeksforgeeks.org/sympy-permutation-parity-in-python/)

**Permutation.parity()** : `parity()` 是一个 sympy Python 库函数，返回置换的奇偶。它意味着置换中逆序数的奇偶性。

> **语法:** `sympy.combinatorics.permutations.Permutation.parity()`
>
> **返回:** 字典奇偶性中的下一个排列

**代码#1: `parity()` 示例**

```py
# Python code explaining
# SymPy.Permutation.parity()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.parity() method

# creating Permutation
a = Permutation([[2, 0], [3, 1]])

b = Permutation([1, 3, 5, 4, 2, 0])

print ("Permutation a - parity form : ", a.parity())
print ("Permutation b - parity form : ", b.parity())
```

**输出:**

> 排列 a–奇偶形式:0
> 排列 b–奇偶形式:1

**代码#2: `parity()` 示例** – 2D 置换

```py
# Python code explaining
# SymPy.Permutation.parity()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.parity() method

# creating Permutation
a = Permutation([[2, 4, 0], 
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - parity form : ", a.parity())
```

**输出:**

> 置换 a–奇偶形式:0