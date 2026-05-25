# python 中的 numpy.bincount()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/num py-bincount-python/

在+ve 整数数组中，`numpy.bincount()`方法计算每个元素的出现次数。每个 bin 值都是其索引的出现。人们也可以相应地设置箱子的大小。

## 语法:

```py
numpy.bincount(arr, weights = None, min_len = 0)
```

## 参数:

```py
arr     : [array_like, 1D]Input array, having positive numbers
weights : [array_like, optional]same shape as that of arr
min_len : Minimum number of bins we want in the output array
```

## 返回:

```py
Output array with no. of occurrence of index value of bin in input - arr. 
Output array, by default is of the length max element of arr + 1\. 
Here size of the output array would be max(input_arr)+1.
```

## 代码 1:NumPy 中 bincount() 的工作

```py
# Python Program explaining 
# working of numpy.bincount() method

import numpy as geek

# 1D array with +ve integers
array1 = [1, 6, 1, 1, 1, 2, 2]
bin = geek.bincount(array1)
print("Bincount output  : \n ", bin)
print("size of bin : ", len(bin), "\n")

array2 = [1, 5, 5, 5, 4, 5, 5, 2, 2, 2]
bin = geek.bincount(array2)
print("Bincount output  : \n ", bin)
print("size of bin : ", len(bin), "\n")

# using min_length attribute
length = 10
bin1 = geek.bincount(array2, None, length)
print("Bincount output  : \n ", bin1)

print("size of bin : ", len(bin1), "\n")
```

## 输出:

```py
Bincount output  : 
  [0 4 2 0 0 0 1]
size of bin :  7

Bincount output  : 
  [0 1 3 0 1 5]
size of bin :  6

Bincount output  : 
  [0 1 3 0 1 5 0 0 0 0]
size of bin :  10
```

## 代码 2:我们可以按 bincount() 权重的元素进行加法运算

```py
# Python Program explaining 
# working of numpy.bincount() method

import numpy as geek

# 1D array with +ve integers
array2 = [10, 11, 4, 6, 2, 1, 9]
array1 = [1, 3, 1, 3, 1, 2, 2]

# array2 : weight
bin = geek.bincount(array1, array2)
print("Summation element-wise : \n", bin)

#index 0 : 0
#index 1 : 10 + 4 + 2 = 16
#index 2 : 1 + 9 = 10
#index 3 : 11 + 6 = 17
```

## 输出:

```py
Summation element-wise : 
 [  0.  16.  10.  17.]
```

## 参考文献:
[https://docs . scipy . org/doc/numpy/reference/generated/numpy . bincount . html # numpy . bincount](https://docs.scipy.org/doc/numpy/reference/generated/numpy.bincount.html#numpy.bincount)

本文由 **Mohit Gupta_OMG 供稿😀** 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。