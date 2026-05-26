# Python 中的 SymPy | Permutation.order()

> 原文: [https://www.geeksforgeeks.org/sympy-permutation-order-in-python/](https://www.geeksforgeeks.org/sympy-permutation-order-in-python/)

`Permutation.order()` 是一个计算排列顺序的 SymPy Python 库函数。当置换被提升到它的阶的幂时，那么，在这种情况下，阶等于单位置换。

> **语法:** `combinatorics.permutations.Permutation.order()`
> **返回:** 排列的顺序

## 代码#1: order() 示例

```py
# Python code explaining
# SymPy.Permutation.order()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.order() method

# creating Permutation
a = Permutation([[2, 0], [3, 1]])

b = Permutation([1, 3, 5, 4, 2, 0])

print ("Permutation a - order form : ", a.order())
print ("Permutation b - order form : ", b.order())
```

**输出:**

> Permutation a - order form: 2
> Permutation b - order form: 6

## 代码#2: order() 示例 – 2D 排列

```py
# Python code explaining
# SymPy.Permutation.order()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.order() method

# creating Permutation
a = Permutation([[2, 4, 0], 
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - order form : ", a.order())
```

**输出:**

> Permutation a - order form: 7