# Python 中的 `numpy.isreal()`

> 哎哎哎:# t0]https://www . geeksforgeeks . org/num py-is-real-python/

`numpy.isreal(数组)`: 逐元素测试它是否为实数(不是无穷大也不是数字)，并将结果作为布尔数组返回。

## 参数:

```py
array : [array_like] Input array whose element we want to test
```

## 返回:

```py
boolean array containing the result
```

## 代码 1 :

```py
# Python Program illustrating
# numpy.isreal() method

import numpy as geek

print("Is Real : ", geek.isreal([1+1j, 0j]), "\n")

print("Is Real : ", geek.isreal([1, 0]), "\n")
```

## 输出:

```py
Is Real :  [False  True]

Is Real :  [ True  True]
```

## 代码 2 :

```py
# Python Program illustrating
# numpy.isreal() method

import numpy as geek

# Returns True/False value for each element 
a = geek.arange(20).reshape(5, 4)
print("Is Real : \n", geek.isreal(a), "\n")

# Returns True/False value as ans 
# because we have mentioned dtpe in the beginning
a = geek.arange(20).reshape(5, 4).dtype = float
print("\nIs Real : ", geek.isreal(a))
```

## 输出:

```py
Is Real : 
 [[ True  True  True  True]
 [ True  True  True  True]
 [ True  True  True  True]
 [ True  True  True  True]
 [ True  True  True  True]]

Is Real :  True
```

## 参考文献:
[https://docs . scipy . org/doc/numpy-dev/reference/generated/numpy . Isreal . html # numpy . Isreal](https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.isreal.html#numpy.isreal)

## 注意:
这些代码不会在在线-ID 上运行。请在您的系统上运行它们来探索工作的。
本文由 **Mohit Gupta_OMG 供稿😀** 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。