# Python 中的 `Permutation.rank()`

> 原文：[https://www.geeksforgeeks.org/sympy-permutation-rank-in-python/](https://www.geeksforgeeks.org/sympy-permutation-rank-in-python/)

`Permutation.rank()` 是一个 SymPy Python 库函数，返回排列的字典排序。

## 语法

`sympy.combinatorics.permutations.Permutation.rank()`

## 返回

排列的字典顺序。

## 代码示例 1：`rank()` 示例

```py
# Python code explaining
# SymPy.Permutation.rank()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.rank() method

# creating Permutation
a = Permutation([[2, 0], [3, 1]])

b = Permutation([1, 3, 5, 4, 2, 0])

print ("Permutation a - rank form : ", a.rank())
print ("Permutation b - rank form : ", b.rank())
```

**输出：**

> Permutation a - rank form : 16
> Permutation b - rank form : 191

## 代码示例 2：`rank()` 示例 – 2D 置换

```py
# Python code explaining
# SymPy.Permutation.rank()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.rank() method

# creating Permutation
a = Permutation([[2, 4, 0], 
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - rank form : ", a.rank())
```

**输出：**

> Permutation a - rank form : 2461