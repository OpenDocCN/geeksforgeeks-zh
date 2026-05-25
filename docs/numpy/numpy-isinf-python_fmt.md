# numpy.isinf() 用法详解

> 参考：[https://www.geeksforgeeks.org/numpy-isinf-python/](https://www.geeksforgeeks.org/numpy-isinf-python/)

`numpy.isinf()` 函数按元素测试是正无穷还是负无穷，并以布尔数组的形式返回结果。

**语法：**
```py
numpy.isinf(array [, out])
```

**参数：**
- `array`：[array_like] 输入数组或对象，需要测试其元素是否为无穷大。
- `out`：[ndarray, optional] 用于存放结果的输出数组。其类型将被保留，并且必须具有正确的形状以容纳输出。

**返回值：**
包含结果的布尔数组。对于标量输入，如果输入是正无穷或负无穷，则返回一个新的布尔值 `True`；否则返回 `False`。对于数组输入，结果是一个与输入形状相同的布尔数组，当输入的对应元素是正无穷或负无穷时，值为 `True`；其他位置为 `False`。

## 代码示例 1

```py
# Python Program illustrating
# numpy.isinf() method

import numpy as geek

print("Finite : ", geek.isinf(1), "\n")

print("Finite : ", geek.isinf(0), "\n")

# not a number
print("Finite : ", geek.isinf(geek.nan), "\n")

#  infinity
print("Finite : ", geek.isinf(geek.inf), "\n")

print("Finite : ", geek.isinf(geek.NINF), "\n")

x = geek.array([-geek.inf, 0., geek.inf])
y = geek.array([2, 2, 2])
print("Checking for infinity : ", geek.isinf(x, y))
```

**输出：**
```py
Finite :  False

Finite :  False

Finite :  False

Finite :  True

Finite :  True

Checking for infinity :  [1 0 1]
```

## 代码示例 2

```py
# Python Program illustrating
# numpy.isinf() method

import numpy as geek

# Returns True/False value for each element
b = geek.arange(8).reshape(2, 4)

print("\n",b)
print("\nIs Infinity : \n", geek.isinf(b))

# geek.inf  : Positive Infinity
# geek.NINF : negative Infinity
b = [[geek.inf],
     [geek.NINF]]
print("\nIs Infinity : \n", geek.isinf(b))
```

**输出：**
```py
 [[0 1 2 3]
 [4 5 6 7]]

Is Infinity : 
 [[False False False False]
 [False False False False]]

Is Infinity : 
 [[ True]
 [ True]]
```

**参考文献：**
[https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.isinf.html#numpy.isinf](https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.isinf.html#numpy.isinf)

**注意：**
这些代码不会在在线编译器上运行。请在您的系统上运行它们来探索工作。

本文由**莫希特·古普塔 _OMG 供稿😀**。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。