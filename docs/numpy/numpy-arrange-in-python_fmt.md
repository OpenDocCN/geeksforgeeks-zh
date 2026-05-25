# Python 中的 `numpy.arange()`

> 原文: [https://www.geeksforgeeks.org/numpy-arrange-in-python/](https://www.geeksforgeeks.org/numpy-arrange-in-python/)

**`numpy.arange([start,] stop[, step,][, dtype])`**： 返回一个数组，其中的元素按照间隔均匀分布。所提到的间隔是半开的，即 `[start, stop]`。

**参数：**

```py
start : [optional] start of interval range. By default start = 0
stop  : end of interval range
step  : [optional] step size of interval. By default step size = 1,  
For any output out, this is the distance between two adjacent values, out[i+1] - out[i]. 
dtype : type of output array
```

**返回：**

```py
Array of evenly spaced values.
Length of array being generated  = Ceil((Stop - Start) / Step) 
```

**示例：**

## 蟒蛇 3

```py
# Python Programming illustrating
# numpy.arange method

import numpy as geek

print("A\n", geek.arange(4).reshape(2, 2), "\n")
print("A\n", geek.arange(4, 10), "\n")
print("A\n", geek.arange(4, 20, 3), "\n")
```

**输出：**

```py
A
 [[0 1]
 [2 3]]

A
 [4 5 6 7 8 9]

A
 [ 4  7 10 13 16 19]
```

**注：**

*   这些 NumPy-Python 程序不会在 onlineID 上运行，所以在您的系统上运行它们来探索它们。
*   `numpy.arange()` 相对于普通内置 `range()` 函数的优势在于，它允许我们生成非整数的数字序列。

**示例：**

## 蟒蛇 3

```py
# Python Programming illustrating
# numpy.arange method

import numpy as np

# Printing all numbers from 1 to
# 2 in steps of 0.1
print(np.arange(1, 2, 0.1))
```

**输出：**

```py
[1.  1.1 1.2 1.3 1.4 1.5 1.6 1.7 1.8 1.9]
```

如果您尝试使用 `range()` 函数，您会得到一个 `TypeError`。

本文由**莫希特·古普塔 _OMG 供稿😀**。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `review-team@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。