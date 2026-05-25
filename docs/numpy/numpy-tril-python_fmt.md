# Python 中的 `numpy.tril()`

> 哎哎哎: https://www.geeksforgeeks.org/numpy-trill-python/

**`numpy.tril(a, k=0)`**：返回三角形下部的数组副本。

## 参数

```py
a : input array
k : [int, optional, 0 by default]
          Diagonal we require; k>0 means diagonal above main diagonal or vice versa.
```

## 返回

```py
Lower triangle of a, having same shape and data-type as a.
```

## 示例

```py
# Python Programming illustrating
# numpy.tril method

import numpy as geek

# string input
a = geek.matrix([[1, 21, 30], 
                 [63 ,434, 3], 
                 [54, 54, 56]])

print("Main Diagonal elements : \n", geek.tril(a), "\n")

print("Diagonal above main Diagonal elements : \n", geek.tril(a, 1), "\n\n")

print("Main Diagonal elements : \n", geek.tril(a, -1))
```

## 输出

```py
Main Diagonal elements : 
 [[  1   0   0]
 [ 63 434   0]
 [ 54  54  56]]

Diagonal above main Diagonal elements : 
 [[  1  21   0]
 [ 63 434   3]
 [ 54  54  56]]

Main Diagonal elements : 
 [[ 0  0  0]
 [63  0  0]
 [54 54  0]]
```

## 参考文献
[https://docs.scipy.org/doc/numpy/reference/generated/numpy.tril.html#numpy.tril](https://docs.scipy.org/doc/numpy/reference/generated/numpy.tril.html#numpy.tril)

**注意:**
这些 NumPy-Python 程序不会在 onlineID 上运行，所以在你的系统上运行它们来探索它们。

本文由 **莫希特·古普塔 _OMG 供稿😀** 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。