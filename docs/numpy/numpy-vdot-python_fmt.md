# python 中的 numpy.vdot()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/num py-vdot-python/

## 先决条件

[Python 中的 `numpy.dot()`](https://www.geeksforgeeks.org/numpy-dot-python/)返回向量 a 和 b 的点积。如果第一个参数是复数，则第一个参数的复共轭（这是`vdot()`不同于`dot()`方法的地方）用于点积的计算。它可以处理多维数组，但作为一个扁平数组工作。

## 参数

1.  `vector_a`: 【array_like】如果 a 是复数，其复共轭用于点积的计算。
2.  `vector_b`: 【array_like】如果 b 是复数，则其复共轭用于点积的计算。

## 返回

向量 a 和 b 的点积

## 代码 1

```py
# Python Program illustrating
# numpy.vdot() method

import numpy as geek

# 1D array
vector_a = 2 + 3j
vector_b = 4 + 5j

product = geek.vdot(vector_a, vector_b)
print("Dot Product  : ", product)
```

## 输出

```py
Dot Product  :  (23-2j)
```

Code1 是如何工作的？
向量_a = 2 + 3j
向量_b = 4 + 5j

按照方法，取向量 a 的共轭，即 2–3j

现在点积= 2(4–5j)+3j(4–5j)
= 8–10j+12j+15
= 23–2j

## 代码 2

```py
# Python Program illustrating
# numpy.vdot() method

import numpy as geek

# 1D array
vector_a = geek.array([[1, 4], [5, 6]])
vector_b = geek.array([[2, 4], [5, 2]])

product = geek.vdot(vector_a, vector_b)
print("Dot Product  : ", product)

product = geek.vdot(vector_b, vector_a)
print("\nDot Product  : ", product)

""" 
How Code 2 works : 
array is being flattened

1 * 2 + 4 * 4 + 5 * 5 + 6 * 2 = 55
"""
```

## 输出

```py
Dot Product  :  55

Dot Product  :  55
```

## 参考文献

[https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.vdot.html#numpy.vdot](https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.vdot.html#numpy.vdot)

。
本文由 <font color="green">**莫希特·古普塔 _OMG 供稿😀**</font> 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。