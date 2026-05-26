# Python 中的 SymPy | Permutation.rmul_with_af()

> 原文: [https://www.geeksforgeeks.org/sympy-permutation-rmul_with_af-in-python/](https://www.geeksforgeeks.org/sympy-permutation-rmul_with_af-in-python/)

`Permutation.rmul_with_af()` 是一个 SymPy Python 库函数，它返回置换的乘积，但参数的元素是具有 `_array_form` 的 `Permutation` 对象。

## 语法

`sympy.combinatorics.permutations.Permutation.rmul_with_af()`

## 返回

排列的乘积。

## 代码示例

### 代码#1 : `rmul_with_af()` 示例

```python
# Python code explaining
# SymPy.Permutation.rmul_with_af()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from sympy.combinatorics.permutations.Permutation.rmul_with_af() method

# creating Permutation
a = Permutation([[2, 0], [3, 1]])

b = Permutation([1, 3, 5, 4, 2, 0])

print ("Permutation a - rmul_with_af form : ", a.rmul_with_af(b))
print ("Permutation b - rmul_with_af form : ", b.rmul_with_af(a))
```

**输出:**

> Permutation a - rmul_with_af form : (0 1 3 4 2 5)
> Permutation b - rmul_with_af form : (0 2)(1 3)

### 代码#2 : `rmul_with_af()` 示例

```python
# Python code explaining
# SymPy.Permutation.rmul_with_af()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from
# sympy.combinatorics.permutations.Permutation.rmul_with_af() method

# creating Permutation
a = Permutation([[2, 4, 0],
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - rmul_with_af form : ", a.rmul_with_af(a))
```

**输出:**

> Permutation a - rmul_with_af form : (0 3 5 6 1 2 4)