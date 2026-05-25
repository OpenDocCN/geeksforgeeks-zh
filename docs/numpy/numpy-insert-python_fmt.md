# Python 中的 `numpy.insert()`

> 哎哎哎:# t0]https://www . geeksforgeeks . org/num py-insert-python/

`numpy.insert()` 函数在给定的索引前沿上述轴插入值。

## 语法:

```py
numpy.insert(array, object, values, axis = None)
```

## 参数:

```py
array   : [array_like]Input array. 
object  : [int, array of ints]Sub-array with the index or indices before 
     which values is inserted
values  : [array_like]values to be added in the arr. Values should be 
     shaped so that arr[...,obj,...] = values. If the type of values is different from 
     that of arr, values is converted to the type of arr
axis    : Axis along which we want to insert the values. By default, it 
     object is applied to flattened array
```

## 返回:

```py
An copy of array with values being inserted as per the mentioned object along a given axis.
```

## 代码 1:从 1D 阵列中删除

```py
# Python Program illustrating
# numpy.insert()

import numpy as geek

#Working on 1D
arr = geek.arange(5)
print("1D arr : \n", arr)
print("Shape : ", arr.shape)

# value = 9
# index = 1   
# Insertion before first index
a = geek.insert(arr, 1, 9)
print("\nArray after insertion : ", a)
print("Shape : ", a.shape)

# Working on 2D array 
arr = geek.arange(12).reshape(3, 4)
print("\n\n2D arr : \n", arr)
print("Shape : ", arr.shape)

a = geek.insert(arr, 1, 9, axis = 1)
print("\nArray after insertion : \n", a)
print("Shape : ", a.shape)
```

## 输出:

```py
1D arr : 
 [0 1 2 3 4]
Shape :  (5,)

Array after insertion :  [0 9 1 2 3 4]
Shape :  (6,)

2D arr : 
 [[ 0  1  2  3]
 [ 4  5  6  7]
 [ 8  9 10 11]]
Shape :  (3, 4)

Array after insertion : 
 [[ 0  9  1  2  3]
 [ 4  9  5  6  7]
 [ 8  9  9 10 11]]
Shape :  (3, 5)
```

## 代码 2:使用标量

```py
# Python Program illustrating
# numpy.insert()

import numpy as geek

# Working on 2D array 
arr = geek.arange(12).reshape(3, 4)
print("2D arr : \n", arr)
print("Shape : ", arr.shape)

# Working with Scalars
a = geek.insert(arr, [1], [[6],[9],], axis = 0)
print("\nArray after insertion : \n", a)
print("Shape : ", a.shape)

# Working with Scalars
a = geek.insert(arr, [1], [[8],[7],[9]], axis = 1)
print("\nArray after insertion : \n", a)
print("Shape : ", a.shape)
```

## 输出:

```py
2D arr : 
 [[ 0  1  2  3]
 [ 4  5  6  7]
 [ 8  9 10 11]]
Shape :  (3, 4)

Array after insertion : 
 [[ 0  1  2  3]
 [ 6  6  6  6]
 [ 9  9  9  9]
 [ 4  5  6  7]
 [ 8  9 10 11]]
Shape :  (5, 4)

Array after insertion : 
 [[ 0  8  1  2  3]
 [ 4  7  5  6  7]
 [ 8  9  9 10 11]]
Shape :  (3, 5)
```

## 代码 3:不同点插入

```py
# Python Program illustrating
# numpy.insert()

import numpy as geek

#Working on 1D
arr = geek.arange(6).reshape(2, 3)
print("1D arr : \n", arr)
print("Shape : ", arr.shape)

# value = 9
# index = 1   
# Insertion before first index
a = geek.insert(arr, (2, 4), 9)
print("\nInsertion at two points : ", a)
print("Shape : ", a.shape)

# Working on 2D array 
arr = geek.arange(12).reshape(3, 4)
print("\n\n2D arr : \n", arr)
print("Shape : ", arr.shape)
a = geek.insert(arr, (0, 3), 66, axis = 1)
print("\nInsertion at two points : \n", a)
print("Shape : ", a.shape)
```

## 输出:

```py
1D arr : 
 [[0 1 2]
 [3 4 5]]
Shape :  (2, 3)

Insertion at two points :  [0 1 9 2 3 9 4 5]
Shape :  (8,)

2D arr : 
 [[ 0  1  2  3]
 [ 4  5  6  7]
 [ 8  9 10 11]]
Shape :  (3, 4)

Insertion at two points : 
 [[66  0  1  2 66  3]
 [66  4  5  6 66  7]
 [66  8  9 10 66 11]]
Shape :  (3, 6)
```

## 参考文献:
[https://docs.scipy.org/doc/numpy/reference/generated/numpy.insert.html#numpy.insert](https://docs.scipy.org/doc/numpy/reference/generated/numpy.insert.html#numpy.insert)

## 注意:
这些代码不会在在线-ID 上运行。请在您的系统上运行它们来探索工作。

本文由 **Mohit Gupta_OMG 供稿😀** 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。