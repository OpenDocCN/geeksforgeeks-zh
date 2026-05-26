# Python 中的 SymPy | Partition.conjugate()

> 原文: [https://www.geeksforgeeks.org/sympy-partition-conjugate-in-python/](https://www.geeksforgeeks.org/sympy-partition-conjugate-in-python/)

`Partition.conjugate()` 是一个 SymPy Python 库函数，返回参数化分区的共轭分区。

## 语法
`sympy.combinatorics.partitions.Partition.conjugate()`

## 返回
共轭分区

## 代码#1: `conjugate()` 示例

```python
# Python code explaining
# SymPy.conjugate()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.partitions import IntegerPartition

# Using from sympy.combinatorics.partitions.Partition.conjugate() method 
p = IntegerPartition([312, 14, 23])
print ('Conjugate : ', p.conjugate)
```

**输出:**

> Conjugate : [3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 3, 2, 2, 2, 2, 2, 2, 2, 2, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1]

## 代码#2: `conjugate()` 示例 – 显示 `ValueError`

```python
# Python code explaining
# SymPy.conjugate()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.partitions import IntegerPartition

# Using from sympy.combinatorics.partitions.Partition.conjugate() method

# Only positive elements are required 
# so this will generate error
p = IntegerPartition([312, 14, -10, 23, -1])
print ('Conjugate : ', p.conjugate)
```

**输出:**

> ValueError: The sum must all be positive.