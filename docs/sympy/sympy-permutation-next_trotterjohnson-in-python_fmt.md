# Python 中的 SymPy | Permutation.next_trotterjohnson()

> 原文: [https://www.geeksforgeeks.org/sympy-permutation-next_trotterjohnson-in-python/](https://www.geeksforgeeks.org/sympy-permutation-next_trotterjohnson-in-python/)

## Permutation.next_trotterjohnson()

`Permutation.next_trotterjohnson()` 是一个 SymPy Python 库函数，返回 Trotter-Johnson 顺序的下一个排列。如果 `self` 是最后一个置换，则返回 `None`。

### 语法

`sympy.combinatorics.permutations.Permutation.next_trotterjohnson()`

### 返回

Trotter-Johnson 顺序的下一个排列。

## 代码示例 #1：next_trotterjohnson() 示例

```py
# Python code explaining
# SymPy.Permutation.next_trotterjohnson()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from
# sympy.combinatorics.permutations.Permutation.next_trotterjohnson() method

# creating Permutation
a = Permutation([[2, 0], [3, 1]])

b = Permutation([1, 3, 5, 4, 2, 0])

print ("Permutation a - next_trotterjohnson form : ", a.next_trotterjohnson())
print ("Permutation b - next_trotterjohnson form : ", b.next_trotterjohnson())
```

**输出:**

> Permutation a – next_trotterjohnson form: (0 3 1 2)
> Permutation b – next_trotterjohnson form: (0 1 5)(2 3 4)

## 代码示例 #2：next_trotterjohnson() 示例 – 2D 置换

```py
# Python code explaining
# SymPy.Permutation.next_trotterjohnson()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from
# sympy.combinatorics.permutations.Permutation.next_trotterjohnson() method

# creating Permutation
a = Permutation([[2, 4, 0],
                 [3, 1, 2],
                 [1, 5, 6]])

print ("Permutation a - next_trotterjohnson form : ", a.next_trotterjohnson())
```

**输出:**

> Permutation a – next_trotterjohnson form: (6)(0 3 5 1 2 4)