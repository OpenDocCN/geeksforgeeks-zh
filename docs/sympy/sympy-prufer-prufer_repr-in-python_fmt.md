# Prufer.prufer_repr() in SymPy (Python)

## 函数描述

`Prufer.prufer_repr()` 是 SymPy Python 库中的一个函数，用于返回 Prufer 对象的 Prufer 序列。该序列通过移除编号最高的顶点，记录其连接的节点，并重复此过程直到仅剩两个顶点来获得。

## 语法与返回值

**语法:**
`sympy.combinatorics.prufer.Prufer.prufer_repr()`

**返回:**
Prufer 对象的 Prufer 序列。

## 代码示例

### 示例 1

```py
# Python code explaining
# SymPy.Prufer.prufer_repr()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.prufer import Prufer

# Using from
# sympy.combinatorics.prufer.Prufer.prufer_repr()

# Creating Prufer
a = Prufer([1, 2, 3], [2, 4, 5])

# prufer_repr value
print ("Prufer a prufer_repr : ", a.prufer_repr)
```

**输出:**

> Prufer a prufer_repr : [1, 2, 3]

### 示例 2

```py
# Python code explaining
# SymPy.Prufer.prufer_repr()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.prufer import Prufer

# Using from
# sympy.combinatorics.prufer.Prufer.prufer_repr()

# Creating Prufer
b = Prufer([1, 2, 3, 2, 4, 5], [6, 7], [8])

# prufer_repr value
print ("Prufer b prufer_repr : ", b.prufer_repr)
```

**输出:**

> Prufer b prufer_repr : [1, 2, 3, 2, 4, 5]