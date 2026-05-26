# 分区.RGS_rank()

> 原文: `https://www.geeksforgeeks.org/sympy-partition-rgs_rank-in-python/`

## 描述

`Partition.RGS_rank(rank, n)` 是一个来自 `sympy` Python 库的函数，它给出了一个受限增长字符串（其中 `a[i]` 是元素 `i` 所在的块的字符串）的排名。

**受限增长字符串** – 一种字符串，其中每个字符 `a_i` 产生对应元素所属的块 `B_i`。

## 语法

```python
sympy.combinatorics.partitions.Partition.rgs_rank()
```

## 返回值

返回受限增长字符串的等级。

## 示例

### 示例1

```python
# Python code explaining
# SymPy.RGS_rank()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.partitions import RGS_rank

# Using from sympy.combinatorics.partitions.Partition.RGS_rank() method 
p = RGS_rank([0, 0, 1, 1, 2])

print ("rank for restricted growth string : \n", p)
```

输出：

> 受限生长字符串的等级:
> 10

### 示例2

```python
# Python code explaining
# SymPy.RGS_rank()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.partitions import RGS_rank

# Using from sympy.combinatorics.partitions.Partition.RGS_rank() method 
p = RGS_rank( [0, 0, 0, 0, 0, 1, 1, 1, 0, 1])

print ("rank for restricted growth string : \n", p)
```

输出：

> 受限生长字符串的等级:
> 100