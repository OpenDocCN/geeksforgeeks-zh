# Python 中的 `numpy.eye()`

> 哎哎哎:# t0]https://www . geeksforgeeks . org/num py-eye-python/

`numpy.eye(R，C = None，k = 0，dtype = type<“float”>):`–`eye`工具返回一个二维数组，对角线为`1`的，其他地方为`0`的。根据可选参数`k`，对角线可以是主对角线、上对角线或下对角线。一个正`k`为上对角线，一个负`k`为下对角线，一个`0 k`（默认）为主对角线。

**参数:**

```py
R : Number of rows
C : [optional] Number of columns; By default M = N
k : [int, optional, 0 by default]
          Diagonal we require; k>0 means diagonal above main diagonal or vice versa.
dtype : [optional, float(by Default)] Data type of returned array.  
```

**返回:**

```py
array of shape, R x C, an array where all elements 
are equal to zero, except for the k-th diagonal, 
whose values are equal to one.
```

**示例:**

## 计算机编程语言

```py
# Python Programming illustrating
# numpy.eye method

import numpy as geek

# 2x2 matrix with 1's on main diagonal
b = geek.eye(2, dtype = float)
print("Matrix b : \n", b)

# matrix with R=4 C=5 and 1 on diagonal
# below main diagonal
a = geek.eye(4, 5, k = -1)
print("\nMatrix a : \n", a)
```

**输出:**

```py
Matrix b : 
 [[ 1\.  0.]
 [ 0\.  1.]]

Matrix a : 
 [[ 0\.  0\.  0\.  0\.  0.]
 [ 1\.  0\.  0\.  0\.  0.]
 [ 0\.  1\.  0\.  0\.  0.]
 [ 0\.  0\.  1\.  0\.  0.]]
```

**注意:**
这些代码不会在在线-ID 上运行。请在您的系统上运行它们来探索工作。

本文由**莫希特·古普塔 _OMG 供稿😀**。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。