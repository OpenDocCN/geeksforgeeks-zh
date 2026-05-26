# Python | SymPy Permutation.get_adjacency_distance()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-permutation-get_adjacency_distance-method/](https://www.geeksforgeeks.org/python-sympy-permutation-get_adjacency_distance-method/)

`Permutation.get_adjacency_distance()` 是一个计算两个置换之间邻接距离的 SymPy Python 库函数。

> **语法:**
> `sympy.combinatorics.permutations.Permutation.get_adjacency_distance()`
>
> **返回:**
> 两个排列之间的邻接距离

## 代码# 1: `get_adjacency_distance()` 示例

```py
# Python code explaining
# SymPy.Permutation.get_adjacency_distance()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from
# sympy.combinatorics.permutations.Permutation.get_adjacency_distance() method

# creating Permutation
a = Permutation([2, 0, 3, 1, 5, 4])

b = Permutation([3, 1, 2, 5, 4, 0])

c = Permutation([0, 1, 3, 4, 5, 2])

print ("a - get_adjacency_distance form b: ", a.get_adjacency_distance(b))
print ("b - get_adjacency_distance form c: ", b.get_adjacency_distance(c))
```

**输出:**

> a–get_adjacency_distance form b: 3
> b–get_adjacency_distance form c: 5

## 代码# 2: `get_adjacency_distance()` 示例 – 2D 置换

```py
# Python code explaining
# SymPy.Permutation.get_adjacency_distance()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from
# sympy.combinatorics.permutations.Permutation.get_adjacency_distance() method

# creating Permutation
a = Permutation([[2, 4, 0],
                 [7, 1, 3],
                 [8, 5, 6]])

b = Permutation([[8, 4, 0],
                 [2, 7, 0],
                 [1, 6, 7]])

print ("a get_adjacency_distance form b : ", a.get_adjacency_distance(b))
```

**输出:**

> a get_adjacency_distance form b : 7