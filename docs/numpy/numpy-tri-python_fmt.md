# numpy.tri()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/num py-tri-python/

`numpy.tri(R, C=None, k=0, dtype='float')`：创建一个在给定对角线（约 `k`）处及其下方有 1，其他地方有 0 的数组。

## 参数

```python
R     : Number of rows
C     : [optional] Number of columns; By default R = C
k     : [int, optional, 0 by default]
               Diagonal we require; k>0 means diagonal above main diagonal or vice versa.
dtype : [optional, float(byDefault)] Data type of returned array.
```

## 示例代码

```python
# Python Program illustrating
# numpy.tri method

import numpy as geek

print("tri with k = 1 : \n",geek.tri(2, 3, 1, dtype = float), "\n")

print("tri with main diagonal : \n",geek.tri(3, 5, 0), "\n")

print("tri with k = -1 : \n",geek.tri(3, 5, -1), "\n")
```

## 输出

```python
tri with k = 1 : 
 [[ 1.  1.  0.]
 [ 1.  1.  1.]]

tri with main diagonal : 
 [[ 1.  0.  0.  0.  0.]
 [ 1.  1.  0.  0.  0.]
 [ 1.  1.  1.  0.  0.]]

tri with k = -1 : 
 [[ 0.  0.  0.  0.  0.]
 [ 1.  0.  0.  0.  0.]
 [ 1.  1.  0.  0.  0.]]
```

## 参考文献

[https://docs.scipy.org/doc/numpy/reference/generated/numpy.tri.html](https://docs.scipy.org/doc/numpy/reference/generated/numpy.tri.html)

## 注意

这些 NumPy-Python 程序不会在 onlineID 上运行，所以在你的系统上运行它们来探索它们。

本文由 **莫希特·古普塔 _OMG 供稿😀** 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。