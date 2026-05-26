# Python | SymPy `Permutation.index()` 方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-permutation-index-method/](https://www.geeksforgeeks.org/python-sympy-permutation-index-method/)

`Permutation.index()` 是一个 SymPy Python 库函数，返回参数中排列的索引值。

**排列的索引** = 所有下标 `j` 的和，使得 `Permutation[j]` 大于 `Permutation[j+1]`。

## 语法
`sympy.combinatorics.permutations.Permutation.index()`

## 返回
排列的索引值。

## 代码示例 1：`index()` 示例

```python
# Python code explaining
# SymPy.Permutation.index()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.index() method

# creating Permutation
a = Permutation([[2, 0], [3, 1]])

b = Permutation([1, 3, 5, 4, 2, 0])

print ("Permutation a - index form : ", a.index())
print ("Permutation b - index form : ", b.index())
```

**输出:**

> Permutation a - index form: 1
> Permutation b - index form: 9

## 代码示例 2：`index()` 示例 – 2D 排列

```python
# Python code explaining
# SymPy.Permutation.index()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.index() method

# creating Permutation
a = Permutation([[2, 4, 0],
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - index form : ", a.index())
```

**输出:**

> Permutation a - index form: 8