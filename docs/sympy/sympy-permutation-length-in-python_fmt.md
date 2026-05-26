# SymPy 中的 Permutation.length()

> 原文: [https://www.geeksforgeeks.org/sympy-permutation-length-in-python/](https://www.geeksforgeeks.org/sympy-permutation-length-in-python/)

`Permutation.length()` 是一个 SymPy Python 库函数，用于查找由排列移动的整数个数。

> **语法:** `sympy.combinatorics.permutations.Permutation.length()`
>
> **返回:** 排列移动的整数个数

## 代码示例 1: `length()` 示例

```py
# Python code explaining
# SymPy.Permutation.length()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.length() method

# creating Permutation
a = Permutation([[2, 0], [3, 1]])

b = Permutation([1, 3, 5, 4, 2, 0])

print ("Permutation a - length form : ", a.length())
print ("Permutation b - length form : ", b.length())
```

**输出:**

> Permutation a - length form : 4
> Permutation b - length form : 6

## 代码示例 2: `length()` 示例 – 2D 置换

```py
# Python code explaining
# SymPy.Permutation.length()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.length() method

# creating Permutation
a = Permutation([[2, 4, 0],
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - length form : ", a.length())
```

**输出:**

> Permutation a - length form : 7