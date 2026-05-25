# numpy.defchararray.multiply() 用法详解

## 函数定义

`numpy.core.defchararray.multiply(arr, n)`：按元素串联字符串 n 次。

## 参数说明

- `arr`：阵列状或弦状。
- `n`：【阵列式】我们要串联的次数。

## 返回值

按元素返回：串联字符串 'n' 次。

## 代码示例 1

```py
# Python Program illustrating 
# numpy.char.multiply() method 
import numpy as np

arr1 = ['eAAAa', 'ttttds', 'AAt']
arr2 = ['11sf', 'sdsf2', '1111f2']

print ("\narr1 : ", arr1)
print ("\narr2 : ", arr2)

print ("\narr1 : ", np.char.multiply(arr1, 2))

# Separate multiplication
print ("\narr1 : ", np.char.multiply(arr1, [2, 4, 3]))
print ("\narr2 : ", np.char.multiply(arr2, 3))
```

## 输出 1

```py
arr1 :  ['eAAAa', 'ttttds', 'AAt']

arr2 :  ['11sf', 'sdsf2', '1111f2']

arr1 :  ['eAAAaeAAAa' 'ttttdsttttds' 'AAtAAt']

arr1 :  ['eAAAaeAAAa' 'ttttdsttttdsttttdsttttds' 'AAtAAtAAt']

arr2 :  ['11sf11sf11sf' 'sdsf2sdsf2sdsf2' '1111f21111f21111f2']
```

## 代码示例 2

```py
# Python Program illustrating 
# numpy.char.multiply() method 
import numpy as np

arr1 = 'This is geeks '
arr2 = 'for geeks '

print ("\narr1 : ", np.char.multiply(arr1, 2))
print ("\narr2 : ", np.char.multiply(arr2, 4))
```

## 输出 2

```py
arr1 :  This is geeks 
arr2 :  for geeks

arr1 :  This is geeks This is geeks 
arr2 :  for geeks for geeks for geeks for geeks
```