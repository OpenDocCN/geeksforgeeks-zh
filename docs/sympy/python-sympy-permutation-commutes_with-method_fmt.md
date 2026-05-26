# Python | SymPy Permutation.commutes_with()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-permutation-commutes_with-method/](https://www.geeksforgeeks.org/python-sympy-permutation-commutes_with-method/)

`Permutation.commutes_with()` 是一个 SymPy Python 库函数，用于检查两个置换是否可交换。假设 `a` 和 `b` 是群 `C` 的一部分，那么 `a` 和 `b` 的换位子就是 `C` 的单位元，**如果 `a` 和 `b` 可交换，即 `ab == ba`。**

## 语法:
`sympy.combinatorics.permutations.Permutation.commutes_with()`

## 返回:
检查两个排列是否在交换。

## 代码#1: `commutes_with()` 示例

```py
# Python code explaining
# SymPy.Permutation.commutes_with()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.commutes_with() method

# creating Permutation
a = Permutation([2, 0, 3, 1, 5, 4])

b = Permutation([3, 1, 2, 5, 4, 0])

print ("Permutation a - commutes_with form : ", a.commutes_with(b))
print ("Permutation b - commutes_with form : ", b.commutes_with(a))
```

## 输出:
> 排列 a–以形式通勤 _ 假
> 排列 b–以形式通勤 _ 假

## 代码#2: `commutes_with()` 示例 – 自换向器

```py
# Python code explaining
# SymPy.Permutation.commutes_with()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.commutes_with() method

# creating Permutation
a = Permutation([[2, 4, 0], 
                 [3, 1, 2],
                 [1, 5, 6]])

# SELF COMMUTATING     
print ("Permutation a - commutes_with form : ", a.commutes_with(a))
```

## 输出:
> 置换 a–用形式通勤 _ 真