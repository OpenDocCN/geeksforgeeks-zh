# SymPy Prufer.prufer_rank() 函数详解

> 吴奇珍: [https://www.geeksforgeeks.org/sympy-prufer-prufer_rank-in-python/](https://www.geeksforgeeks.org/sympy-prufer-prufer_rank-in-python/)

## Prufer.prufer_rank() 函数

`Prufer.prufer_rank()` 是一个 SymPy Python 库函数，用于计算一个 Prufer 序列的秩。

### 语法

```python
Prufer.prufer_rank()
```

### 返回值

返回 Prufer 序列的秩。

## 代码示例 1：prufer_rank() 示例

```py
# Python code explaining
# SymPy.Prufer.prufer_rank()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.prufer import Prufer

# Using from
# sympy.combinatorics.prufer.Prufer.prufer_rank()

# Creating Prufer
a = Prufer([1, 2, 3], [2, 4, 5])

# prufer_rank value
print ("Prufer a prufer_rank : ", a.prufer_rank())
```

**输出:**

```
Prufer a prufer_rank : 38
```

## 代码示例 2：prufer_rank() 示例

```py
# Python code explaining
# SymPy.Prufer.prufer_rank()

# importing SymPy libraries
from sympy.combinatorics import Permutation, Cycle
from sympy.combinatorics.prufer import Prufer

# Using from
# sympy.combinatorics.prufer.Prufer.prufer_rank()

# Creating Prufer
b = Prufer([1, 2, 3, 2, 4, 5], [6, 7], [8])

# prufer_rank value
print ("Prufer b prufer_rank : ", b.prufer_rank())
```

**输出:**

```
Prufer b prufer_rank : 42661
```