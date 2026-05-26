# Python 中的 SymPy | Permutation.is_even()

> 原文: [https://www.geeksforgeeks.org/sympy-permutation-is_even-in-python/](https://www.geeksforgeeks.org/sympy-permutation-is_even-in-python/)

`Permutation.is_even()` 是一个 sympy Python 库函数，检查排列是否为偶数。

> **语法:** `sympy.combinatorics.permutations.Permutation.is_even()`
>
> **返回:** `true` – 如果排列是偶数；否则为假

**代码#1 : `is_even()` 示例**

```py
# Python code explaining
# SymPy.Permutation.is_even()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.is_even() method

# creating Permutation
a = Permutation([[2, 0], [3, 1]])

b = Permutation([1, 3, 5, 4, 2, 0])

print ("Permutation a - is_even form : ", a.is_even)
print ("Permutation b - is_even form : ", b.is_even)
```

**输出:**

> 排列 a – is_even 形式: 真
> 排列 b – is_even 形式: 假

**代码#2 : `is_even()` 示例** – 2D 置换

```py
# Python code explaining
# SymPy.Permutation.is_even()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.is_even() method

# creating Permutation
a = Permutation([[2, 4, 0], 
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - is_even form : ", a.is_even)
```

**输出:**

> 排列 a – is_even 形式: 真