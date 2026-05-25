# Python 中的 `numpy.flip()`

> 哎哎哎:# t0]https://www . geeksforgeeks . org/num py-flip-python/

`numpy.flip()` 函数沿指定轴反转数组元素的顺序，保持数组的形状。

```py
Syntax: numpy.flip(array, axis)
```

## 参数:

```py
array : [array_like]Array to be input 
axis  : [integer]axis along which array 
        is reversed.
```

## 返回:

```py
reversed array with shape preserved
```

```py
# Python Program illustrating
# numpy.flip() method

import numpy as geek

array = geek.arange(8).reshape((2,2,2))
print("Original array : \n", array)

print("Flipped array : \n", geek.flip(array, 0))
```

## 输出:

```py
Original array : 
 [[[0 1]
  [2 3]]

[[4 5]
  [6 7]]]

Flipped array : 
 [[[4, 5]
  [6, 7]]

[[0, 1]
  [2, 3]]]
```

## 参考文献:
[https://docs . scipy . org/doc/numpy-dev/reference/generated/numpy . flip . html # numpy . flip](https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.flip.html#numpy.flip)

## 注意:
这些代码不会在在线-ID 上运行。请在您的系统上运行它们来探索工作的。
本文由 <font color="green">**Mohit Gupta_OMG 供稿😀**</font> 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。