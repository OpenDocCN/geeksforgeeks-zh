# Python 中的 `numpy.empty()`

> 原文: [https://www.geeksforgeeks.org/numpy-empty-python/](https://www.geeksforgeeks.org/numpy-empty-python/)

## 函数介绍

`numpy.empty(shape, dtype = float, order = 'C')`：返回给定形状和类型的新数组，带有随机值。

## 参数说明

- `shape`：行数。
- `order`：`C_contiguous` 或 `F_contiguous`。
- `dtype`：[可选，`float`(默认)] 返回数组的数据类型。

## 代码示例

```py
# Python Programming illustrating
# numpy.empty method

import numpy as geek

b = geek.empty(2, dtype = int)
print("Matrix b : \n", b)

a = geek.empty([2, 2], dtype = int)
print("\nMatrix a : \n", a)

c = geek.empty([3, 3])
print("\nMatrix c : \n", c)
```

## 输出结果

```py
Matrix b : 
 [         0 1079574528]

Matrix a : 
 [[0 0]
 [0 0]]

Matrix a : 
 [[ 0.  0.  0.]
 [ 0.  0.  0.]
 [ 0.  0.  0.]]
```

## 注意事项

与 `numpy.zeros()` 不同，`empty` 不会将数组值设置为零，因此可能会稍微快一些。
此外，这些代码可能不会在在线编译器上运行。请在您的系统上运行它们来探索工作原理。

本文由 **Mohit Gupta_OMG** 供稿😀。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。