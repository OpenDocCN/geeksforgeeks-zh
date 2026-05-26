# Python 中的 SymPy | Permutation.random()

> 原文: [https://www.geeksforgeeks.org/sympy-permutation-random-in-python/](https://www.geeksforgeeks.org/sympy-permutation-random-in-python/)

## Permutation.random()

`Permutation.random()` 是一个 SymPy Python 库函数，返回长度为 `n` 的随机置换。

> **语法:** `sympy.combinatorics.permutations.Permutation.random()`
>
> **返回:** 长度为 `n` 的随机排列

## 代码#1: random() 示例

```py
# Python code explaining
# SymPy.Permutation.random()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.random() method

# creating Permutation
a = Permutation([[2, 0], [3, 1]])

b = Permutation([1, 3, 5, 4, 2, 0])

print ("Permutation a - random form : ", a.random(2))
print ("Permutation b - random form : ", b.random(5))
```

### 输出

> Permutation a - random form : (1)
> Permutation b - random form : (4)

## 代码#2: random() 示例 – 2D 置换

```py
# Python code explaining
# SymPy.Permutation.random()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from
# sympy.combinatorics.permutations.Permutation.random() method

# creating Permutation
a = Permutation([[2, 4, 0],
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - random form : ", a.random(4))
```

### 输出

> Permutation a - random form : (0 1 2 3)