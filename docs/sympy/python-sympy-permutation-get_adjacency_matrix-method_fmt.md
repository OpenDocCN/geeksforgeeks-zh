# Python | SymPy Permutation.get_adjacency_matrix()方法

> 原文: [https://www.geeksforgeeks.org/python-sympy-permutation-get_adjacency_matrix-method/](https://www.geeksforgeeks.org/python-sympy-permutation-get_adjacency_matrix-method/)

`Permutation.get_adjacency_matrix()` 是一个 SymPy Python 库函数，用于计算给定置换的邻接矩阵。

## 语法
```python
sympy.combinatorics.permutations.Permutation.get_adjacency_matrix()
```

## 返回
计算置换的邻接矩阵。

## 代码示例 1：get_adjacency_matrix() 示例

```py
# Python code explaining
# SymPy.Permutation.get_adjacency_matrix()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from
# sympy.combinatorics.permutations.Permutation.get_adjacency_matrix() method

# creating Permutation
a = Permutation([2, 0, 3, 1, 5, 4])

b = Permutation([3, 1, 2, 5, 4, 0])

print ("a - get_adjacency_matrix : \n", a.get_adjacency_matrix())
print ("b - get_adjacency_matrix : \n", b.get_adjacency_matrix())
```

**输出:**
```
a - get_adjacency_matrix :
 Matrix([[0, 0, 0, 1, 0, 0],
        [0, 0, 0, 0, 0, 1],
        [1, 0, 0, 0, 0, 0],
        [0, 1, 0, 0, 0, 0],
        [0, 0, 0, 0, 0, 1],
        [0, 0, 1, 0, 0, 0]])

b - get_adjacency_matrix :
 Matrix([[0, 0, 0, 0, 0, 1],
        [0, 0, 1, 0, 0, 0],
        [0, 0, 0, 0, 0, 1],
        [0, 1, 0, 0, 0, 0],
        [1, 0, 0, 0, 0, 0],
        [0, 0, 0, 1, 0, 0]])
```

## 代码示例 2：get_adjacency_matrix() 示例 – 2D 置换

```py
# Python code explaining
# SymPy.Permutation.get_adjacency_matrix()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.permutations import Permutation

# Using from
# sympy.combinatorics.permutations.Permutation.get_adjacency_matrix() method

# creating Permutation
a = Permutation([[2, 4, 0],
                 [7, 1, 3],
                 [8, 5, 6]])

b = Permutation([[8, 4, 0],
                 [2, 7, 0],
                 [1, 6, 7]])

print ("a get_adjacency_matrix : \n", a.get_adjacency_matrix())

print ("\nb get_adjacency_matrix : \n", b.get_adjacency_matrix())
```

**输出:**
```
a get_adjacency_matrix :
 Matrix([[0, 0, 0, 0, 0, 0, 1, 0, 0],
        [0, 0, 0, 0, 0, 0, 0, 1, 0],
        [0, 0, 0, 1, 0, 0, 0, 0, 0],
        [0, 0, 0, 0, 0, 0, 1, 0, 0],
        [0, 0, 0, 0, 0, 0, 0, 0, 1],
        [0, 0, 0, 0, 0, 0, 0, 0, 1],
        [0, 0, 0, 0, 0, 0, 0, 0, 0],
        [0, 0, 0, 0, 0, 0, 0, 0, 0],
        [0, 0, 0, 0, 0, 0, 0, 0, 0]])

b get_adjacency_matrix :
 Matrix([[0, 0, 0, 0, 1, 0, 0, 0, 0],
        [0, 0, 0, 1, 0, 0, 0, 0, 0],
        [0, 0, 0, 0, 0, 1, 0, 0, 0],
        [0, 0, 1, 0, 0, 0, 0, 0, 0],
        [0, 0, 0, 0, 0, 0, 0, 0, 0],
        [0, 0, 0, 0, 0, 0, 0, 0, 0],
        [0, 0, 0, 0, 0, 0, 0, 0, 0],
        [0, 0, 0, 0, 0, 0, 0, 0, 0],
        [0, 0, 0, 0, 0, 0, 0, 0, 0]])
```