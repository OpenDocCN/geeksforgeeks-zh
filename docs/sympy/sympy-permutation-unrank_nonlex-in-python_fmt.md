# Python 中的 SymPy | Permutation.unrank_nonlex()

> 原文: [https://www.geeksforgeeks.org/sympy-permutation-unrank_nonlex-in-python/](https://www.geeksforgeeks.org/sympy-permutation-unrank_nonlex-in-python/)

`Permutation.unrank_nonlex()` 是一个 SymPy Python 库函数，是一个不尊重字典顺序的线性时间解开算法。

> **语法:** `sympy.combinatorics.permutations.Permutation.unrank_nonlex()`
>
> **返回:** 线性时间解开。

## 代码# 1: `unrank_nonlex()` 示例

```py
# Python code explaining
# SymPy.Permutation.unrank_nonlex()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from
# sympy.combinatorics.permutations.Permutation.unrank_nonlex() method

# creating Permutation
a = Permutation([[2, 0], [3, 1]])

b = Permutation([1, 3, 5, 4, 2, 0])

print ("Permutation a - unrank_nonlex form : ", a.unrank_nonlex(2, 5))
print ("Permutation b - unrank_nonlex form : ", b.unrank_nonlex(1, 6))
```

**输出:**

> Permutation a - unrank_nonlex form : (1)
> Permutation b - unrank_nonlex form : (0)

## 代码# 2: `unrank_nonlex()` 示例

```py
# Python code explaining
# SymPy.Permutation.unrank_nonlex()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from
# sympy.combinatorics.permutations.Permutation.unrank_nonlex() method

# creating Permutation
a = Permutation([[2, 4, 0],
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - unrank_nonlex form : ", a.unrank_nonlex(2, 8))
```

**输出:**

> Permutation a - unrank_nonlex form : (0 1)