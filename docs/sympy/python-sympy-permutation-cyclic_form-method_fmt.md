# Python | SymPy Permutation.cyclic_form()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-permutation-cyclic_form-method/](https://www.geeksforgeeks.org/python-sympy-permutation-cyclic_form-method/)

`Permutation.cyclic_form()` 是一个 SymPy Python 库函数，通过省略单元素循环，从规范形式返回循环符号表示。

> **语法:**
> `sympy.combinatorics.permutations.Permutation.cyclic_form()`
>
> **从规范形式返回:**
> 循环符号表示

## 代码#1: `cyclic_form()` 示例

```py
# Python code explaining
# SymPy.Permutation.cyclic_form()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.cyclic_form() method

# creating Permutation
a = Permutation([2, 0, 3, 1, 5, 4])

b = Permutation([3, 1, 2, 5, 4, 0])

print ("Permutation a - cyclic_form form : ", a.cyclic_form)
print ("Permutation b - cyclic_form form : ", b.cyclic_form)
```

**输出:**

> Permutation a - cyclic_form form : [[0, 2, 3, 1], [4, 5]]
> Permutation b - cyclic_form form : [[0, 3, 5]]

## 代码#2: `cyclic_form()` 示例 – 2D 置换

```py
# Python code explaining
# SymPy.Permutation.cyclic_form()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from
# sympy.combinatorics.permutations.Permutation.cyclic_form() method

# creating Permutation
a = Permutation([[2, 4, 0],
                 [3, 1, 2],
                 [1, 5, 6]])

# SELF COMMUTATING
print ("Permutation a - cyclic_form form : ", a.cyclic_form)
```

**输出:**

> Permutation a - cyclic_form form : [[0, 3, 5, 6, 1, 2, 4]]