# Python 中的 `numpy.full_like()`

> 原文: [https://www.geeksforgeeks.org/numpy-full_like-python/](https://www.geeksforgeeks.org/numpy-full_like-python/)

`numpy.full_like()` 函数返回一个与给定数组具有相同形状和类型的新数组。

## 语法

```py
numpy.full_like(a, fill_value, dtype=None, order='K', subok=True)
```

## 参数

```py
shape : Number of rows
order : C_contiguous or F_contiguous
dtype : [optional, float(by Default )] Data type of returned array.  
subok : [bool, optional] to make subclass of a or not
```

## 返回

```py
ndarray
```

## 示例

```py
# Python Programming illustrating
# numpy.full_like method

import numpy as geek

x = geek.arange(10, dtype=int).reshape(2, 5)
print("x before full_like : \n", x)

# using full_like
print("\nx after full_like : \n", geek.full_like(x, 10.0))

y = geek.arange(10, dtype=float).reshape(2, 5)
print("\n\ny before full_like : \n", x)

# using full_like
print("\ny after full_like : \n", geek.full_like(y, 0.01))
```

## 输出

```py
x before full_like : 
 [[0 1 2 3 4]
 [5 6 7 8 9]]

x after full_like : 
 [[10 10 10 10 10]
 [10 10 10 10 10]]

y before full_like : 
 [[0 1 2 3 4]
 [5 6 7 8 9]]

y after full_like : 
 [[ 0.01  0.01  0.01  0.01  0.01]
 [ 0.01  0.01  0.01  0.01  0.01]]
```

## 引用

[https://docs.scipy.org/doc/numpy/reference/generated/numpy.full_like.html#numpy.full_like](https://docs.scipy.org/doc/numpy/reference/generated/numpy.full_like.html#numpy.full_like)

## 注意

这些代码不会在 online-ID 上运行。请在您的系统上运行它们来探索工作方式。

本文由 **莫希特·古普塔 _OMG 供稿😀** 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。