# Python | SymPy `Permutation.inversion_vector()`

> 原文: [https://www.geeksforgeeks.org/python-sympy-permutation-inversion_vector/](https://www.geeksforgeeks.org/python-sympy-permutation-inversion_vector/)

`Permutation.inversion_vector()` 是一个 SymPy Python 库函数，返回参数中排列的 `inversion_vector` 值。反转向量包括那些其值指示排列中的元素数量的元素，它们是小于它并且位于它的右侧。

## 语法
`sympy.combinatorics.permutations.Permutation.inversion_vector()`

## 返回
排列的逆向量值。

## 代码示例 #1：`inversion_vector()` 示例

```py
# Python code explaining
# SymPy.Permutation.inversion_vector()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.inversion_vector() method

# creating Permutation
a = Permutation([[2, 0], [3, 1]])

b = Permutation([1, 3, 5, 4, 2, 0])

print ("Permutation a - inversion_vector form : ", a.inversion_vector())
print ("Permutation b - inversion_vector form : ", b.inversion_vector())
```

**输出:**

排列 a–反转向量形式: [2, 2, 0]
排列 b–反转向量形式: [1, 2, 3, 2, 1]

## 代码示例 #2：`inversion_vector()` 示例 – 2D 置换

```py
# Python code explaining
# SymPy.Permutation.inversion_vector()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.inversion_vector() method

# creating Permutation
a = Permutation([[2, 4, 0], 
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - inversion_vector form : ", a.inversion_vector())
```

**输出:**

排列 a–反转向量形式: [3, 2, 2, 2, 0, 1]