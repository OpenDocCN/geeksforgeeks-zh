# Python中的`numpy.asmatrix()`

> 哎哎哎:# t0]https://www.geeksforgeeks.org/numpy-asmatrix-python/

通过将输入解释为矩阵来返回矩阵。

**参数:**

```py
data  : array-like input data 
dtype : Data type of returned array
```

**返回:**

```py
Interprets the input as a matrix
```

```py
# Python Programming illustrating
# numpy.asmatrix

import numpy as geek

# array-like input
b = geek.matrix([[5, 6, 7], [4, 6]])
print("Via array-like input : \n", b, "\n")

c = geek.asmatrix(b)
b[0, 1] = 10
print("c matrix : \n", c)
```

**输出:**

```py
Via array-like input : 
 [[[5, 6, 7] [4, 6]]]

c matrix : 
 [[[5, 6, 7] 10]]

```

**注意:** 这些 NumPy-Python 程序不会在 onlineID 上运行，所以在你的系统上运行它们来探索它们。

本文由<font color="green">莫希特·古普塔 _OMG 供稿😀</font> 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。