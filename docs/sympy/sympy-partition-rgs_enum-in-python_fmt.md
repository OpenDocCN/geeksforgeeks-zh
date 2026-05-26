# SymPy 中的 Partition.RGS_enum()

> 原文: [https://www.geeksforgeeks.org/sympy-partition-rgs_enum-in-python/](https://www.geeksforgeeks.org/sympy-partition-rgs_enum-in-python/)

## 函数介绍

`Partition.RGS_enum()` 是 SymPy 库中的一个函数，用于计算大小为 `n` 的集合上可能的**受限增长字符串**的总数。

**受限增长字符串** 是一种字符串，其中每个字符 `a[i]` 表示元素 `i` 所属的块 `B[i]`。

## 语法与返回值

**语法:**
`sympy.combinatorics.partitions.Partition.RGS_enum()`

**返回:**
返回一个整数，表示大小为 `n` 的集合上可能的受限增长字符串的总数。

## 代码示例

### 示例 1

```py
# Python code explaining
# SymPy.RGS_enum()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.partitions import RGS_enum

# Using from sympy.combinatorics.partitions.Partition.RGS_enum() method 
p = RGS_enum(4)

q = RGS_enum(9)

print ("no. of strings possible for size  4: ", p)
print ("no. of strings possible for size  9: ", q)
```

**输出:**

> no. of strings possible for size  4:  15
> no. of strings possible for size  9:  203

### 示例 2

```py
# Python code explaining
# SymPy.RGS_enum()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.partitions import RGS_enum

# Using from sympy.combinatorics.partitions.Partition.RGS_enum() method 
p = RGS_enum(20)

q = RGS_enum(-1)

print ("no. of strings possible for size  20 ", p)
print ("no. of strings possible for size  -1: ", q)
```

**输出:**

> no. of strings possible for size  20  51724158235372
> no. of strings possible for size  -1:  0