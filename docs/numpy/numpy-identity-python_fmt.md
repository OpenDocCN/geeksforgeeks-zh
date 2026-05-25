# Python 中的 `numpy.identity()`

> 原文:[https://www.geeksforgeeks.org/numpy-identity-python/](https://www.geeksforgeeks.org/numpy-identity-python/)

`numpy.identity(n，dtype = None)` : 返回一个恒等式矩阵，即主对角线上有 1 的正方形矩阵。

```py
Parameters : 
n     : [int] Dimension n x n of output array  
dtype : [optional, float(by Default)] Data type of returned array.  
```

```py
Returns : 
identity array of dimension n x n,  with its main diagonal set to one, and all other elements 0.
```

## 示例:

```py
# Python Programming illustrating
# numpy.identity method

import numpy as geek

# 2x2 matrix with 1's on main diagonal
b = geek.identity(2, dtype = float)
print("Matrix b : \n", b)

a = geek.identity(4)
print("\nMatrix a : \n", a)
```

### 输出:

```py
Matrix b : 
 [[ 1.  0.]
 [ 0.  1.]]

Matrix a : 
 [[ 1.  0.  0.  0.]
 [ 0.  1.  0.  0.]
 [ 0.  0.  1.  0.]
 [ 0.  0.  0.  1.]]
```

### 注意:
这些代码不会在在线-ID 上运行。请在您的系统上运行它们来探索工作。
本文由**莫希特·古普塔 _OMG 供稿😀**。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。