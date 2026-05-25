# NumPy矩阵的`cumprod()`方法

> 原文链接: https://www.geeksforgeeks.org/python-numpy-matrix-cumprod/

借助`Numpy matrix.cumprod()`方法，我们能够找到给定矩阵的`cumulative product`，并以一维矩阵的形式给出输出。

> **语法:** `matrix.cumprod()`
> 
> **返回:** 返回矩阵的累计乘积

**示例 #1:**
在这个示例中，我们可以看到借助于`matrix.cumprod()`方法，我们能够找到给定矩阵的累积积。

```py
# import the important module in python
import numpy as np

# make matrix with numpy
gfg = np.matrix('[6, 2, 3]')

# applying matrix.cumprod() method
geeks = gfg.cumprod()

print(geeks)
```

**输出:**

```py
[[ 6 12 36]]
```

**示例 #2:**

```py
# import the important module in python
import numpy as np

# make a matrix with numpy
gfg = np.matrix('[1, 2, 3; 4, 5, 6]')

# applying matrix.cumprod() method
geeks = gfg.cumprod()

print(geeks)
```

**输出:**

```py
[[  1   2   6  24 120 720]]
```