# Python中的`numpy.append()`

> 哎哎哎:# t0]https://www . geeksforgeeks . org/num py-append-python/

`numpy.append()`在数组末尾沿着所述轴追加值。

## 语法

```py
numpy.append(array, values, axis = None)
```

## 参数

```py
array   : [array_like]Input array. 
values  : [array_like]values to be added in the arr. Values should be 
     shaped so that arr[...,obj,...] = values. If the axis is defined values can be of any
     shape as it will be flattened before use.
axis    : Axis along which we want to insert the values. By default, array
     is flattened.
```

## 返回值

```py
An copy of array with values being appended at the end as per the mentioned object
along a given axis.
```

## 代码示例

### 追加数组

```py
# Python Program illustrating
# numpy.append()

import numpy as geek

#Working on 1D
arr1 = geek.arange(5)
print("1D arr1 : ", arr1)
print("Shape : ", arr1.shape)

arr2 = geek.arange(8, 12)
print("\n1D arr2 : ", arr2)
print("Shape : ", arr2.shape)

# appending the arrays
arr3 = geek.append(arr1, arr2)
print("\nAppended arr3 : ", arr3)
```

**输出:**

```py
1D arr1 :  [0 1 2 3 4]
Shape :  (5,)

1D arr2 :  [ 8  9 10 11]
Shape :  (4,)

Appended arr3 :  [ 0  1  2  3  4  8  9 10 11]
```

### 玩轴

```py
# Python Program illustrating
# numpy.append()

import numpy as geek

#Working on 1D
arr1 = geek.arange(8).reshape(2, 4)
print("2D arr1 : \n", arr1)
print("Shape : ", arr1.shape)

arr2 = geek.arange(8, 16).reshape(2, 4)
print("\n2D arr2 : \n", arr2)
print("Shape : ", arr2.shape)

# appending the arrays
arr3 = geek.append(arr1, arr2)
print("\nAppended arr3 by flattened : ", arr3)

# appending the arrays with axis = 0
arr3 = geek.append(arr1, arr2, axis = 0)
print("\nAppended arr3 with axis 0 : \n", arr3)

# appending the arrays with axis = 1
arr3 = geek.append(arr1, arr2, axis = 1)
print("\nAppended arr3 with axis 1 : \n", arr3)
```

**输出:**

```py
2D arr1 : 
 [[0 1 2 3]
 [4 5 6 7]]
Shape :  (2, 4)

2D arr2 : 
 [[ 8  9 10 11]
 [12 13 14 15]]
Shape :  (2, 4)

Appended arr3 by flattened :  [ 0  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15]

Appended arr3 with axis 0 : 
 [[ 0  1  2  3]
 [ 4  5  6  7]
 [ 8  9 10 11]
 [12 13 14 15]]

Appended arr3 with axis 1 : 
 [[ 0  1  2  3  8  9 10 11]
 [ 4  5  6  7 12 13 14 15]]
```

## 参考文献
[https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.append.html#numpy.append](https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.append.html#numpy.append)。

本文由 **Mohit Gupta_OMG 供稿😀**。如果你喜欢GeeksforGeeks并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。