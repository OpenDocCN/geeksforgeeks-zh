# SymPy Permutation.full_cyclic_form() 方法

> 原文：[https://www.geeksforgeeks.org/python-sympy-permutation-full_cyclic_form-method/](https://www.geeksforgeeks.org/python-sympy-permutation-full_cyclic_form-method/)

`Permutation.full_cyclic_form()` 是一个 SymPy Python 库函数，通过包含单元素循环以循环形式返回置换。

## 语法

```python
sympy.combinatorics.permutations.Permutation.full_cyclic_form()
```

## 返回值

循环形式的置换。

## 代码示例 1：full_cyclic_form() 示例

```python
# Python code explaining
# SymPy.Permutation.full_cyclic_form()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.full_cyclic_form() method

# creating Permutation
a = Permutation([2, 0, 3, 1, 5, 4])

b = Permutation([3, 1, 2, 5, 4, 0])

print ("Permutation a - full_cyclic_form form : ", a.full_cyclic_form)
print ("Permutation b - full_cyclic_form form : ", b.full_cyclic_form)
```

**输出：**

> Permutation a - full_cyclic_form form : [[0, 2, 3, 1], [4, 5]]
> Permutation b - full_cyclic_form form : [[0, 3, 5], [1], [2], [4]]

## 代码示例 2：full_cyclic_form() 示例 – 2D 置换

```python
# Python code explaining
# SymPy.Permutation.full_cyclic_form()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from
# sympy.combinatorics.permutations.Permutation.full_cyclic_form() method

# creating Permutation
a = Permutation([[2, 4, 0],
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - full_cyclic_form form : ", a.full_cyclic_form)
```

**输出：**

> Permutation a - full_cyclic_form form : [[0, 3, 5, 6, 1, 2, 4]]