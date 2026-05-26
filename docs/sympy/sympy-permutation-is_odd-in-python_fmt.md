# Python 中的 SymPy | `Permutation.is_odd()`

> 原文: [https://www.geeksforgeeks.org/sympy-permutation-is_odd-in-python/](https://www.geeksforgeeks.org/sympy-permutation-is_odd-in-python/)

`Permutation.is_odd()` 是一个 SymPy Python 库函数，用于检查排列是否为奇数。

## 语法
```python
sympy.combinatorics.permutations.Permutation.is_odd()
```

## 返回值
`True` – 如果排列是奇数；否则为 `False`。

## 代码示例 1：`is_odd()` 示例
```python
# Python code explaining
# SymPy.Permutation.is_odd()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.is_odd() method

# creating Permutation
a = Permutation([[2, 0], [3, 1]])

b = Permutation([1, 3, 5, 4, 2, 0])

print ("Permutation a - is_odd form : ", a.is_odd)
print ("Permutation b - is_odd form : ", b.is_odd)
```

**输出:**
> 排列 a – 是奇数形式: `False`
> 排列 b – 是奇数形式: `True`

## 代码示例 2：`is_odd()` 示例 – 2D 置换
```python
# Python code explaining
# SymPy.Permutation.is_odd()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.is_odd() method

# creating Permutation
a = Permutation([[2, 4, 0], 
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - is_odd form : ", a.is_odd)
```

**输出:**
> 排列 a – is_odd 形式: `False`