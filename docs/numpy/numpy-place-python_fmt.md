# numpy.place()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/num py-place-python/

`numpy.place()` 方法根据参数–条件和值对数组进行更改(根据用户设置的掩码，使用前 N 个值放入数组)。它的工作原理与 [`numpy.extract()`](https://www.geeksforgeeks.org/numpy-extract-python/) 相反。

## 语法

```py
numpy.place(array, mask, vals) 
```

## 参数

```py
array : [ndarray] Input array, we need to make changes into
mask  : [array_like]Boolean that must have same size as that of the input array
value : Values to put into the array. Based on the mask condition it adds only N-elements
    to the array. If in case values in val are smaller than the mask, same values get repeated.
```

## 返回

```py
Array with change elements i.e. new elements being put
```

## 示例

```py
# Python Program illustrating
# numpy.place() method

import numpy as geek

array = geek.arange(12).reshape(3, 4)
print("Original array : \n", array)

# Putting new elements
a = geek.place(array, array > 5, [15, 25, 35])
print("\nPutting up elements to array: \n", array)

array1 = geek.arange(6).reshape(2, 3)
print("\n\nOriginal array1 : \n", array)

# Putting new elements
a = geek.place(array1, array1>2, [44, 55])
print("\nPutting new elements to array1 : \n", array1)
```

## 输出

```py
Original array : 
 [[ 0  1  2  3]
 [ 4  5  6  7]
 [ 8  9 10 11]]

Putting up elements to array: 
 [[ 0  1  2  3]
 [ 4  5 15 25]
 [35 15 25 35]]

Original array1 : 
 [[ 0  1  2  3]
 [ 4  5 15 25]
 [35 15 25 35]]

Putting new elements to array1 : 
 [[ 0  1  2]
 [44 55 44]]
```

## 参考文献

[https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.place.html#numpy.place](https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.place.html#numpy.place)

## 注意

这些代码不会在在线-ID 上运行。请在您的系统上运行它们来探索工作。

本文由 **Mohit Gupta_OMG 供稿😀** 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。