# numpy.iscomplex() 用法详解

> 哎哎哎:# t0]https://www . geeksforgeeks . org/num py-isccomplect-python/

`numpy.iscomplex()` 函数逐元素测试它是否是复数(不是无穷大也不是数字)，并将结果作为布尔数组返回。

## 语法:

```py
numpy.iscomplex(array)
```

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
# numpy.iscomplex() method

import numpy as geek

print("Is Complex : ", geek.iscomplex([1+1j, 1+0j]), "\n")

print("Is Complex : ", geek.iscomplex([0+1j, 0]), "\n")
```

## 输出:

```py
Is Complex :  [ True False]

Is Complex :  [ True False]
```

## 代码 2 :

```py
# Python Program illustrating
# numpy.iscomplex() method

import numpy as geek

# Returns True/False value for each element 
a = geek.arange(20).reshape(5, 4)
print("Is complex : \n", geek.iscomplex(a))

# Returns True/False value as ans 
# because we have mentioned dtpe in the beginning
b = geek.arange(20).reshape(5, 4).dtype = complex

print("\n",b)
print("\nIs complex : ", geek.iscomplex(b))

b = [[1j], 
     [3]]
print("\nIs complex : \n", geek.iscomplex(b))
```

## 输出:

```py
Is complex : 
 [[False False False False]
 [False False False False]
 [False False False False]
 [False False False False]
 [False False False False]]

Is complex :  False

Is complex : 
 [[ True]
 [False]]
```

## 参考文献:
[https://docs . scipy . org/doc/numpy-dev/reference/generated/numpy . is inite . html](https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.isfinite.html)

## 注意:
这些代码不会在在线-ID 上运行。请在您的系统上运行它们来探索工作。
本文由<font color="green">莫希特·古普塔 _OMG 供稿😀</font> 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。