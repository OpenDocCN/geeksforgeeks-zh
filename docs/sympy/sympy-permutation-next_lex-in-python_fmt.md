# SymPy 中的 Permutation.next_lex()

> 原文: [https://www.geeksforgeeks.org/sympy-permutation-next_lex-in-python/](https://www.geeksforgeeks.org/sympy-permutation-next_lex-in-python/)

`Permutation.next_lex()` 是一个 SymPy Python 库函数，它返回字典顺序中的下一个排列，如果 `self` 是字典顺序中的最后一个排列，则返回 `None`。

> **语法:** `sympy.combinatorics.permutations.Permutation.next_lex()`
> **返回:** 字典顺序中的下一个排列

## 代码示例 1：`next_lex()` 基本用法

```python
# Python code explaining
# SymPy.Permutation.next_lex()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.next_lex() method

# creating Permutation
a = Permutation([[2, 0], [3, 1]])

b = Permutation([1, 3, 5, 4, 2, 0])

print ("Permutation a - next_lex form : ", a.next_lex())
print ("Permutation b - next_lex form : ", b.next_lex())
```

**输出:**

> Permutation a – next_lex form: (0 2 1 3)
> Permutation b – next_lex form: (5)(0 1 4 3 2)

## 代码示例 2：`next_lex()` 与二维排列

```python
# Python code explaining
# SymPy.Permutation.next_lex()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.next_lex() method

# creating Permutation
a = Permutation([[2, 4, 0], 
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - next_lex form : ", a.next_lex())
```

**输出:**

> Permutation a – next_lex form: (6)(0 3 5)(1 2 4)