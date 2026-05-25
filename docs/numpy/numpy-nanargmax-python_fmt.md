# numpy.nanargmax()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/num py-nanahrgmax-python/

`numpy.nanargmax()` 函数返回数组中最大元素在特定轴上的索引，忽略 `NaNs`。
如果切片只包含 `NaNs` 和 `Infs`，则结果不可信。

## 语法

```py
numpy.nanargmax(array, axis = None) 
```

## 参数

```py
array : Input array to work on 
axis  : [int, optional]Along a specified axis like 0 or 1
```

## 返回

```py
Array of indices into the array with same shape as array.shape
 with the dimension along axis removed.
```

## 代码 1：计算

```py
# Python Program illustrating
# working of nanargmax()

import numpy as geek

# Working on 1D array
array = [geek.nan, 4, 2, 3, 1]
print("INPUT ARRAY 1 : \n", array)

array2 = geek.array([[geek.nan, 4], [1, 3]])

# returning Indices of the max element
# as per the indices ingnoring NaN
print("\nIndices of max in array1 : ", geek.nanargmax(array))

# Working on 2D array
print("\nINPUT ARRAY 2 : \n", array2)
print("\nIndices of max in array2 : ", geek.nanargmax(array2))

print("\nIndices at axis 1 of array2 : ", geek.nanargmax(array2, axis = 1))
```

## 输出

```py
INPUT ARRAY 1 : 
 [nan, 4, 2, 3, 1]

Indices of max in array1 :  1

INPUT ARRAY 2 : 
 [[ nan   4.]
 [  1\.   3.]]

Indices of max in array2 :  1

Indices at axis 1 of array2 :  [1 1]
```

## 代码 2：比较 `argmax` 和 `nanargmax` 的工作情况

```py
# Python Program illustrating
# working of nanargmax()

import numpy as geek

# Working on 2D array
array = ( [[ 8, 13, 5, 0],
           [ 16, geek.nan, 5, 3],
           [geek.nan, 7, 15, 15],
           [3, 11, 4, 12]])
print("INPUT ARRAY : \n", array)

# returning Indices of the max element
# as per the indices

'''  
   [[ 8 13  5  0]
   [ 16  2  5  3]
   [10  7 15 15]
   [ 3 11  4 12]]
     ^  ^  ^  ^

'''

print("\nIndices of max using argmax : ", geek.argmax(array, axis = 0))
print("\nIndices of max using nanargmax :  : ", geek.nanargmax(array, axis = 0))
```

## 输出

```py
INPUT ARRAY : 
 [[8, 13, 5, 0], [16, nan, 5, 3], [nan, 7, 15, 15], [3, 11, 4, 12]]

Indices of max using argmax :  [2 1 2 2]

Indices of max using nanargmax :  :  [1 0 2 2]
```

## 参考资料
[https://docs . scipy . org/doc/num py-dev/reference/generad/num py . nana rgmax . html # num py . nana rgmax](https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.nanargmax.html#numpy.nanargmax)

## 注意
这些代码不会在在线-ID 上运行。请在您的系统上运行它们来探索工作。

本文由**莫希特·古普塔 _OMG 供稿😀**。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。