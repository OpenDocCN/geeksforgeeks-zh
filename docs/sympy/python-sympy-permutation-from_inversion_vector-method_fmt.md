# Python SymPy Permutation.from_inversion_vector()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-permutation-from_inversion_vector-method/](https://www.geeksforgeeks.org/python-sympy-permutation-from_inversion_vector-method/)

`Permutation.from_inversion_vector()` 是一个 SymPy Python 库函数，返回来自反转向量的置换。
**反转向量** – 排列中第 i 个元素左侧的元素数量 > 给出了反转向量的第 i 个元素。

## 语法
```python
sympy.combinatorics.permutations.Permutation.from_inversion_vector()
```

## 返回
反转向量的排列。

## 代码示例 1：from_inversion_vector() 示例
```py
# Python code explaining
# SymPy.from_inversion_vector()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from 
# sympy.combinatorics.permutations.Permutation.from_inversion_vector() method

# creating vectors
a = [1, 0, 0, 0]

b = [6, 5, 4, 3, 0, 0 ]

# inversion forms
print ("vector a - from_inversion_vector form : ", 
       Permutation.from_inversion_vector(a))
print ("vector b - from_inversion_vector form : ", 
       Permutation.from_inversion_vector(b))
```

**输出:**
> 向量 a – from_inversion_vector 形式: `Permutation([1, 0], size=5)`
> 向量 b – from_inversion_vector 形式: `Permutation([6, 5, 4, 3, 0, 1, 2])`

## 代码示例 2：from_inversion_vector() 示例
```py
# Python code explaining
# SymPy.from_inversion_vector()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from 
# sympy.combinatorics.permutations.Permutation.from_inversion_vector() method

# creating vector
a = [2, 3, 1, 0]

# inverted vector of a
print ("vector a - from_inversion_vector form : ", 
       Permutation.from_inversion_vector(a))
```

**输出:**
> 向量 a – from_inversion_vector 形式: `Permutation([2, 4, 1, 0, 3])`