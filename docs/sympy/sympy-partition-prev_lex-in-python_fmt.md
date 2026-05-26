# Partition.prev_lex() in Python

> 原文: `https://www.geeksforgeeks.org/sympy-partition-prev_lex-in-python/`

`Partition.prev_lex()` 是一个 SymPy Python 库函数，返回上一个整数分区，`n` 按字典序（lexographical）排列。如果分区是 `[1, …, 1]`，这种排序将环绕到 `[n]`。

> **语法:** `sympy.combinatorics.partitions.Partition.prev_lex()`
>
> **返回:** 前一个整数分区，`n` 按字典序排列。

## 代码示例 1：`prev_lex()`

```python
# Python code explaining
# SymPy.prev_lex()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.partitions import IntegerPartition

# Using from sympy.combinatorics.partitions.Partition.prev_lex() method
p = IntegerPartition([312, 121, 14, 5])

print('p : ', p)
print('\nPrevious Integrer : ', p.prev_lex())
```

**输出:**

> p : [312, 121, 14, 5]
>
> 上一次积分 ： [312, 121, 14, 4, 1]

## 代码示例 2：`prev_lex()`

```python
# Python code explaining
# SymPy.prev_lex()

# importing SymPy libraries
from sympy.combinatorics.partitions import Partition
from sympy.combinatorics.partitions import IntegerPartition

# Using from sympy.combinatorics.partitions.Partition.prev_lex() method
p = IntegerPartition([1, 312, 121, 14,
                      34, 56, 32])

print('p : ', p)
print('\nPrevious Integrer : ', p.prev_lex())
```

**输出:**

> p : [312, 121, 56, 34, 32, 14, 1]
>
> 上一次积分 ： [312, 121, 56, 34, 32, 13, 2]