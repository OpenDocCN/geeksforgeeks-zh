# Python 中的 `numpy.any()`

> 原文:[https://www.geeksforgeeks.org/numpy-any-in-python/](https://www.geeksforgeeks.org/numpy-any-in-python/)

`numpy.any()` 函数测试沿着所述轴的任何数组元素是否评估为真。

## 语法:

```py
numpy.any(a,
          axis = None,
          out = None,
          keepdims = class numpy._globals._NoValue at 0x40ba726c)
```

## 参数:

```py
array    :[array_like]Input array or object whose elements, we need to test.
axis     : [int or tuple of ints, optional]Axis along which array elements 
     are evaluated.
     The default (axis = None) is to perform a logical AND over all the dimensions of the input
     array. Axis may be negative, in which case it counts from the last to the first axis.
out      : [ndarray, optional]Output array with same dimensions as Input array, 
     placed with result
keepdmis : [boolean, optional]If this is set to True, the axes which are 
     reduced are left in the result as dimensions with size one. With this option, the result 
     will broadcast correctly against the input array.
     If the default value is passed, then keepdims will not be passed through to the all 
     method of sub-classes of ndarray, however any non-default value will be. If the 
     sub-classes sum method does not implement keepdims any exceptions will be raised.
```

## 返回:

```py
A new Boolean array as per 'out' parameter
```

## 代码 1 :

```py
# Python Program illustrating
# numpy.any() method

import numpy as geek

# Axis = NULL 
#  True    False
#  True    True
#  True  : False  =  True (OR)

print("Bool Value with axis = NONE  : ",
      geek.any([[True,False],[True,True]]))

# Axis = 0 
#  True    False
#  True    True
#  True  : False
print("\nBool Value with axis = 0  : ",
      geek.any([[True,False],[True,True]], axis = 0))

print("\nBool : ", geek.any([-1, 4, 5]))

# Not a Number (NaN), positive infinity and negative infinity 
# evaluate to True because these are not equal to zero.
print("\nBool : ", geek.any([1.0, geek.nan]))

print("\nBool Value : ", geek.any([[0, 0],[0, 0]]))
```

## 输出:

```py
Bool Value with axis = NONE  :  True

Bool Value with axis = 0  :  [ True  True]

Bool :  True

Bool :  True

Bool Value :  False
```

## 代码 2 :

```py
# Python Program illustrating
# numpy.any() method

# Parameter : keepdmis

import numpy as geek

# setting keepdmis = True
print("\nBool Value : ", geek.any([[1, 0],[0, 4]], True))

# setting keepdmis = True
print("\nBool Value : ", geek.any([[0, 0],[0, 0]], False))
```

## 输出:

```py
Bool Value :  [ True  True]

Bool Value :  [False False]
VisibleDeprecationWarning: using a boolean instead of an integer 
will result in an error in the future
return umr_any(a, axis, dtype, out, keepdims)
```

## 参考文献:
[https://docs . scipy . org/doc/numpy-dev/reference/generated/numpy . any . html # numpy . any](https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.any.html#numpy.any)

## 注意:
这些代码不会在在线-ID 上运行。请在您的系统上运行它们来探索工作。

本文由 <font color="green">**Mohit Gupta_OMG 供稿😀**</font> 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。