# Python 中的 SymPy | `Permutation.is_Identity()`

> 原文: [https://www.geeksforgeeks.org/sympy-permutation-is_identity-in-python/](https://www.geeksforgeeks.org/sympy-permutation-is_identity-in-python/)

## `Permutation.is_Identity()`

`is_Identity()` 是一个 sympy Python 库函数，用于检查排列是否是一个恒等置换。

> **语法:** `sympy.combinatorics.permutations.Permutation.is_Identity()`
>
> **返回:** `true` – 如果该置换是一个恒等置换；否则为 `false`

### 代码#1: `is_Identity()` 示例

```py
# Python code explaining
# SymPy.Permutation.is_Identity()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.is_Identity() method

# creating Permutation
a = Permutation([[2, 0], [3, 1]])

b = Permutation([1, 3, 5, 4, 2, 0])

print ("Permutation a - is_Identity form : ", a.is_Identity)
print ("Permutation b - is_Identity form : ", b.is_Identity)
```

**输出:**

> Permutation a - is_Identity form : False
> Permutation b - is_Identity form : False

### 代码#2: `is_Identity()` 示例 – 2D 置换

```py
# Python code explaining
# SymPy.Permutation.is_Identity()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.is_Identity() method

# creating Permutation
a = Permutation([[2, 4, 0], 
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - is_Identity form : ", a.is_Identity)
```

**输出:**

> Permutation a - is_Identity form : False