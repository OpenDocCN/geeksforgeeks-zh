# numpy.diag_indices() 用法详解

> 原文链接：[https://www.geeksforgeeks.org/numpy-diag_indices-python/](https://www.geeksforgeeks.org/numpy-diag_indices-python/)

`numpy.diag_indices()` 函数返回索引，以便访问最小维数等于 2 的数组的主对角线元素。它以元组的形式返回索引，用于访问数组的主对角线。

**语法：**
```py
numpy.diag_indices(n, n_dim=2)
```

**参数:**
```py
n : 数组的大小，需要沿每个维度获取对角线元素的索引。
n_dim : [int, optional] 维度数量。
```

**返回:**
```py
用于访问对角线元素的索引（以元组形式返回）。
```

## 示例 1：基本用法

```py
# Python 程序演示
# diag_indices() 的用法

import numpy as geek

# 创建一个 5 X 5 数组并返回主对角线元素的索引
d = geek.diag_indices(5)
print("对角线元素的索引（元组形式）：")
print(d, "\n")

array = geek.arange(16).reshape(4,4)
print("初始数组：\n", array)

# 通过访问对角线元素来操作对角线元素
d = geek.diag_indices(4)
array[d] = 25
print("\n新数组：\n", array)
```

**输出:**
```py
对角线元素的索引（元组形式）：
(array([0, 1, 2, 3, 4]), array([0, 1, 2, 3, 4]))

初始数组：
 [[ 0  1  2  3]
 [ 4  5  6  7]
 [ 8  9 10 11]
 [12 13 14 15]]

新数组：
 [[25  1  2  3]
 [ 4 25  6  7]
 [ 8  9 25 11]
 [12 13 14 25]]
```

## 示例 2：操作二维数组

```py
# Python 程序演示
# diag_indices() 的用法

import numpy as geek

# 操作一个 2D 数组
d = geek.diag_indices(3, 2)

array = geek.arange(12).reshape(4, 3)

array[d] = 111
print("操作后的数组：\n", array)
```

**输出:**
```py
操作后的数组：
 [[111   1   2]
 [  3 111   5]
 [  6   7 111]
 [  9  10  11]]
```

## 示例 3：操作三维数组

```py
# Python 程序演示
# diag_indices() 的用法

import numpy as geek

# 设置对角线索引
d = geek.diag_indices(1, 2)
print("对角线索引：\n", d)

# 创建一个所有元素为 1 的 3D 数组
array = geek.ones((2, 2, 2), dtype=geek.int)
print("初始数组：\n", array)

# 操作一个 3D 数组
array[d] = 0
print("新数组：\n", array)
```

**输出:**
```py
对角线索引：
 (array([0]), array([0]))
初始数组：
 [[[1 1]
  [1 1]]

[[1 1]
  [1 1]]]
新数组：
 [[[0 0]
  [1 1]]

[[1 1]
  [1 1]]]
```

**参考文献:**
[https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.diag_indices.html](https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.diag_indices.html)

**注意:**
这些代码不会在在线 IDE 上运行。请在您的系统上运行它们来探索功能。

本文由 **Mohit Gupta_OMG😀** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章，或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。