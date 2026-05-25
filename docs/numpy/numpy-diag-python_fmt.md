# python 中的 `numpy.diag()`

> 哎哎哎:# t0]https://www . geeksforgeeks . org/num py-diag-python/

### `numpy.diag(a，k=0)` : 提取并构建对角数组

### 参数:

```py
a : array_like 
k : [int, optional, 0 by default]
          Diagonal we require; k>0 means diagonal above main diagonal or vice versa.
```

### 返回:

```py
ndarray
```

## 计算机编程语言

```py
# Python Programming illustrating
# numpy.diag method

import numpy as geek

# matrix creation by array input
a = geek.matrix([[1, 21, 30],
                 [63 ,434, 3],
                 [54, 54, 56]])

print("Main Diagonal elements : \n", geek.diag(a), "\n")

print("Diagonal above main diagonal : \n", geek.diag(a, 1), "\n")

print("Diagonal below main diagonal : \n", geek.diag(a, -1))
```

### 输出:

```py
Main Diagonal elements : 
 [  1 434  56]

Diagonal above main diagonal : 
 [21  3]

Diagonal below main diagonal : 
 [63 54]
```

### 参考文献:
[https://docs . scipy . org/doc/NumPy/reference/generated/NumPy . diag flat . html # NumPy . diag flat](https://docs.scipy.org/doc/numpy/reference/generated/numpy.diagflat.html#numpy.diagflat)

### 注意:
这些 NumPy-Python 程序不会在 onlineID 上运行，所以在你的系统上运行它们来探索它们。
本文由**莫希特·古普塔 _OMG 供稿😀**。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。