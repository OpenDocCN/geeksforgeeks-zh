# Python 中的 `numpy.empty_like()`

> 原文:[https://www.geeksforgeeks.org/numpy-empty_like-python/](https://www.geeksforgeeks.org/numpy-empty_like-python/)

`numpy.empty_like(a，dtype = None，order = 'K '，subok = True) :` 返回与给定数组具有相同形状和类型的新数组。

参数:

```py
shape : Number of rows
order : C_contiguous or F_contiguous
dtype : [optional, float(by Default)] Data type of returned array.  
subok : [bool, optional] to make subclass of a or not
```

返回:

```py
array with the same shape and type as a given array.
```

```py
# Python Program illustrating
# numpy.empty_like method

import numpy as geek

a = geek.empty_like([2, 2], dtype = int)
print("\nMatrix a : \n", a)

c = a = ([1,2,3], [4,5,6])
print("\nMatrix c : \n", geek.empty_like(c))
```

输出:

```py
Matrix a : 
 [  16843008 1058682594]

Matrix c : 
 [[0 0 0]
 [0 0 0]]
```

注意:
这些代码不会在在线-ID 上运行。请在您的系统上运行它们来探索工作。

本文由 <font color="green">**Mohit Gupta_OMG 供稿😀**</font> 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。