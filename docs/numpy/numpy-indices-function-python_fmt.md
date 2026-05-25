# `numpy.indices()` 函数 – Python

> 原文: [https://www.geeksforgeeks.org/numpy-indices-function-python/](https://www.geeksforgeeks.org/numpy-indices-function-python/)

`numpy.indices()` 函数返回一个代表网格索引的数组。计算一个数组，其中子数组包含仅沿相应轴变化的索引值 0，1，…。

## 语法
`numpy.indices(dimensions, dtype, sparse=False)`

## 参数
- `dimensions`: 【ints 序列】网格的形状。
- `dtype`: 【数据类型，可选】结果的数据类型。
- `sparse`: 【布尔，可选】返回网格的稀疏表示，而不是密集表示。默认值为假。

## 返回值
【数组或数组元组】
- 如果 `sparse` 为假:
  返回一个网格索引数组，`grid.shape = (len(dimensions),) + tuple(dimensions)`。
- 如果 `sparse` 为真:
  返回数组的元组，带有 `grid[i].shape = (1, …, 1, dimensions[i], 1, …, 1)`，`dimensions[i]` 在第 `i` 个位置。

## 代码示例 1

```py
# Python program explaining
# numpy.indices() function

# importing numpy as geek 
import numpy as geek

gfg = geek.indices((2, 3))

print (gfg)
```

**输出:**

```py
[[[0 0 0]
  [1 1 1]]

[[0 1 2]
  [0 1 2]]]
```

## 代码示例 2

```py
# Python program explaining
# numpy.indices() function

# importing numpy as geek 
import numpy as geek

grid = geek.indices((2, 3))
gfg = grid[1]

print (gfg)
```

**输出:**

```py
[[0 1 2]
 [0 1 2]]
```