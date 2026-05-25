# Python 中的 `numpy.flipud()`

> 哎哎哎:# t0]https://www . geeksforgeeks . org/num py-flipped-python/

`numpy.flipud()` 函数将数组（每列中的条目）上下翻转，形状保持不变。

## 语法:

```py
numpy.flipud(array)
```

## 参数:

```py
array : [array_like]Input array, we want to flip
```

## 返回:

```py
Flipped array in up-down direction.
```

## 示例

```py
# Python Program illustrating
# numpy.flipud() method

import numpy as geek

array = geek.arange(8).reshape((2,2,2))
print("Original array : \n", array)

# flipud : means flip up-down
print("\nFlipped array : \n", geek.flipud(array))
```

## 输出:

```py
Original array : 
 [[[0 1]
  [2 3]]

[[4 5]
  [6 7]]]

Flipped array : 
 [[[4 5]
  [6 7]]

[[0 1]
  [2 3]]]
```

## 参考文献:
[https://docs . scipy . org/doc/numpy-dev/reference/generated/numpy . flipud . html # numpy . flipud](https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.flipud.html#numpy.flipud)

## 注意:
这些代码不会在在线-ID 上运行。请在您的系统上运行它们来探索工作的。
本文由 <font color="green">**Mohit Gupta_OMG 供稿😀**</font> 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。