# Python 中的 SymPy | Permutation.min()

> 原文：`https://www.geeksforgeeks.org/sympy-permutation-min-in-python/`

`Permutation.min()` 是一个 SymPy Python 库函数，返回置换中的最小值。

## 语法

> `sympy.combinatorics.permutations.Permutation.min()`

## 返回值

> 置换中的最小值

## 代码示例 #1：min() 示例

```py
# Python code explaining
# SymPy.Permutation.min()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.min() method

# creating Permutation
a = Permutation([[2, 0], [3, 1]])

b = Permutation([1, 3, 5, 4, 2, 0])

print ("Permutation a - min form : ", a.min())
print ("Permutation b - min form : ", b.min())
```

**输出：**

> Permutation a - min form : 0
> Permutation b - min form : 0

## 代码示例 #2：min() 示例 – 2D 置换

```py
# Python code explaining
# SymPy.Permutation.min()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.min() method

# creating Permutation
a = Permutation([[2, 4, 0], 
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - min form : ", a.min())
```

**输出：**

> Permutation a - min form : 0