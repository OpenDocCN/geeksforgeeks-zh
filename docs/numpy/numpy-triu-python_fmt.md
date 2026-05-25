# 在 Python 中的 `numpy.triu()`

> 哎哎哎:# t0]https://www . geeksforgeeks . org/num py-triu-python/

## 参数

```py
a : input array
k : [int, optional, 0 by default]
          Diagonal we require; k>0 means diagonal above main diagonal or vice versa.
```

## 返回

```py
Upper triangle of a, having same shape and data-type as a.
```

## 示例

```py
# Python Programming illustrating
# numpy. triu method

import numpy as geek

# string input
a = geek.matrix([[1, 21, 30], 
                 [63 ,434, 3], 
                 [54, 54, 56]])

print("Main Diagonal elements : \n", geek. triu(a), "\n")

print("Diagonal above main Diagonal elements : \n", geek. triu(a, 1), "\n\n")

print("Main Diagonal elements : \n", geek. triu(a, -1))
```

## 输出

```py
Main Diagonal elements : 
 [[  1  21  30]
 [  0 434   3]
 [  0   0  56]]

Diagonal above main Diagonal elements : 
 [[ 0 21 30]
 [ 0  0  3]
 [ 0  0  0]]

Main Diagonal elements : 
 [[  1  21  30]
 [ 63 434   3]
 [  0  54  56]]
```

## 参考

[https://docs.scipy.org/doc/numpy/reference/generated/numpy.triu.html#numpy.triu](https://docs.scipy.org/doc/numpy/reference/generated/numpy.triu.html#numpy.triu)

## 注意

这些 NumPy-Python 程序不会在在线 ID 上运行，所以在你的系统上运行它们来探索它们。

本文由 **莫希特·古普塔 _OMG 供稿😀** 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。