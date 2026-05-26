# SymPy Permutation.mul_inv() 方法详解

> 原文：[https://www.geeksforgeeks.org/sympy-permutation-mul_inv-in-python/](https://www.geeksforgeeks.org/sympy-permutation-mul_inv-in-python/)

`Permutation.mul_inv()` 是 SymPy Python 库中的一个函数，用于返回乘法逆 `other*~self`，前提是 `self` 和 `other` 都具有 `_array_form`。

> **语法：** `sympy.combinatorics.permutations.Permutation.mul_inv()`
>
> **返回：** 乘法逆 `other*~self`，其中 `self` 和 `other` 都具有 `_array_form`。

## 代码示例 1：`mul_inv()` 基本用法

```python
# Python code explaining
# SymPy.Permutation.mul_inv()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from
# sympy.combinatorics.permutations.Permutation.mul_inv() method

# creating Permutation
a = Permutation([[2, 0], [3, 1]])

b = Permutation([1, 3, 5, 4, 2, 0])

print ("Permutation a - mul_inv form : ", a.mul_inv(a))
print ("Permutation b - mul_inv form : ", b.mul_inv(b))
```

**输出：**

> Permutation a - mul_inv form : (3)
> Permutation b - mul_inv form : (5)

## 代码示例 2：`mul_inv()` 用于二维置换

```python
# Python code explaining
# SymPy.Permutation.mul_inv()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.mul_inv() method

# creating Permutation
a = Permutation([[2, 4, 0],
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - mul_inv form : ", a.mul_inv(a))
```

**输出：**

> Permutation a - mul_inv form : (6)