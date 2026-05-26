# 症状|分区。Python 中的 `RGS_unrank()`

> 原文: [https://www.geeksforgeeks.org/sympy-partition-rgs_unrank-in-python/](https://www.geeksforgeeks.org/sympy-partition-rgs_unrank-in-python/)

## `Partition.RGS_unrank(rank, n)`

`RGS_unrank()` 是一个 SymPy Python 库函数，为大小为 `n` 的超集提供 `unrank` 受限增长字符串（字符串，其中 `a[i]` 是元素 `i` 所在的块）。

**限制生长字符串** – 字符串，其中每个字符 `a_i` 产生对应元素所属的块 `B_i`。

### 语法

`sympy.combinatorics.partitions.Partition.RGS_unrank()`

### 返回

`n` 大小超集的限制生长字符串。

### 代码示例 1：`RGS_unrank()` 示例

```py
# Python code explaining
# SymPy.RGS_unrank()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.partitions import RGS_unrank

# Using from sympy.combinatorics.partitions.Partition.RGS_unrank() method
rank = 10
n = 5
p = RGS_unrank(rank, n)

print ("unranked restricted growth string for super size 10 : \n", p)
```

**输出:**

> 超大小 10 的未链接受限增长字符串:
> [0, 0, 1, 1, 2]

### 代码示例 2：`RGS_unrank()` 示例

```py
# Python code explaining
# SymPy.RGS_unrank()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.partitions import RGS_unrank

# Using from sympy.combinatorics.partitions.Partition.RGS_unrank() method
p = RGS_unrank(100, 10)

print ("unranked restricted growth string for super size 10 : \n", p)
```

**输出:**

> 超大小 10 的未链接受限增长字符串:
> [0, 0, 0, 0, 0, 1, 1, 1, 0, 1]