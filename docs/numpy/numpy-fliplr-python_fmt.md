# numpy.fliplr()

`numpy.fliplr(array)`：左右方向翻转数组（各列条目），形状保留。

## 参数

`array` : `[array_like]` 输入数组，我们想要翻转。

## 返回

左右方向翻转后的数组。

```py
# Python Program illustrating
# numpy.fliplr() method

import numpy as geek

array = geek.arange(8).reshape((2,2,2))
print("Original array : \n", array)

# fliplr : means flip left-right
print("\nFlipped array left-right : \n", geek.fliplr(array))
```

## 输出

```py
Original array : 
 [[[0 1]
  [2 3]]

[[4 5]
  [6 7]]]

Flipped array left-right : 
 [[[2 3]
  [0 1]]

[[6 7]
  [4 5]]]
```

## 参考文献

[https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.fliplr.html#numpy.fliplr](https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.fliplr.html#numpy.fliplr)

## 注意

这些代码不会在在线-ID上运行。请在您的系统上运行它们来探索工作的。

本文由 **Mohit Gupta_OMG 供稿😀**。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。