# NumPy 字符串运算：`greater_equal()` 函数

> 原文：[https://www.geeksforgeeks.org/numpy-string-operations-greater_equal-function/](https://www.geeksforgeeks.org/numpy-string-operations-greater_equal-function/)

## 函数介绍

`numpy.core.defchararray.greater_equal(arr1, arr2)` 是 NumPy 中用于字符串比较的函数。它逐个检查两个形状相同的字符串数组的元素，如果 `arr1` 的元素大于或等于 `arr2` 的元素（即 `arr1 >= arr2`），则返回 `True`；否则返回 `False`。

## 参数

- `arr1`：字符串或 Unicode 类型的类数组对象，作为第一个输入数组。
- `arr2`：字符串或 Unicode 类型的类数组对象，作为第二个输入数组。

## 返回值

`ndarray`：布尔类型的输出数组。如果输入是标量，则返回单个布尔值。

## 代码示例

### 代码 #1

```py
# Python program explaining
# numpy.char.greater_equal() method

# importing numpy 
import numpy as geek

# input arrays  
in_arr1 = geek.array('numpy')
print ("1st Input array : ", in_arr1)
in_arr2 = geek.array('nump')
print ("2nd Input array : ", in_arr2)

# checking if in_arr1 >= in_arr2
out_arr = geek.char.greater_equal(in_arr1, in_arr2)
print ("Output array: ", out_arr) 
```

**输出：**

```py
1st Input array :  numpy
2nd Input array :  nump
Output array:  True
```

### 代码 #2

```py
# Python program explaining
# numpy.char.greater_equal() method

# importing numpy 
import numpy as geek

# input arrays  
in_arr1 = geek.array(['Geeks', 'for', 'Geek', 'Numpy'])
print ("1st Input array : ", in_arr1) 
in_arr2 = geek.array(['Geek', 'for', 'Geek', 'numpy'])
print ("2nd Input array : ", in_arr2)

# checking if in_arr1 >= in_arr2
out_arr = geek.char.greater_equal(in_arr1, in_arr2)
print ("Output array: ", out_arr) 
```

**输出：**

```py
1st Input array :  ['Geeks' 'for' 'Geek' 'Numpy']
2nd Input array :  ['Geek' 'for' 'Geek' 'numpy']
Output array:  [ True  True  True False]
```

### 代码 #3

```py
# Python program explaining
# numpy.char.greater_equal() method

# importing numpy 
import numpy as geek

# input arrays  
in_arr1 = geek.array(['10', '11', '122', '15'])
print ("1st Input array : ", in_arr1) 
in_arr2 = geek.array(['10', '13', '121', '141'])
print ("2nd Input array : ", in_arr2)

# checking if in_arr1 >= in_arr2
out_arr = geek.char.greater_equal(in_arr1, in_arr2)
print ("Output array: ", out_arr) 
```

**输出：**

```py
1st Input array :  ['10' '11' '122' '15']
2nd Input array :  ['10' '13' '121' '141']
Output array:  [ True False  True  True]
```