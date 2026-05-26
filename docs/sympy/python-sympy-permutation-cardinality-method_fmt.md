# Python | SymPy 置换.cardinality()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-permutation-cardinality-method/](https://www.geeksforgeeks.org/python-sympy-permutation-cardinality-method/)

`Permutation.cardinality()`是一个`sympy` Python库函数，返回所有可能的排列个数。

> **语法:** `sympy.combinatorics.permutations.Permutation.cardinality()`
> **返回:** 所有可能的排列数

## 代码#1: cardinality()示例

```py
# Python code explaining
# SymPy.Permutation.cardinality()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.cardinality() method

# creating Permutation
a = Permutation([[2, 0], [3, 1]])

b = Permutation([1, 3, 5, 4, 2, 0])

print ("Permutation a - cardinality form : ", a.cardinality)
print ("Permutation b - cardinality form : ", b.cardinality)
```

**输出:**

> Permutation a - cardinality form: 24
> Permutation b - cardinality form: 720

## 代码#2: cardinality()示例 – 2D置换

```py
# Python code explaining
# SymPy.Permutation.cardinality()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.cardinality() method

# creating Permutation
a = Permutation([[2, 4, 0], 
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - cardinality form : ", a.cardinality)
```

**输出:**

> Permutation a - cardinality form: 5040