# numpy 字符串操作 | `isnumeric()`函数

> 原文: [https://www.geeksforgeeks.org/numpy-string-operations-isnumeric-function/](https://www.geeksforgeeks.org/numpy-string-operations-isnumeric-function/)

`numpy.core.defchararray.isnumeric(arr)`函数如果只有数字字符并且至少有一个字符，则为每个元素返回 `true`。否则返回 `false`。

## 参数
`arr` : 类似字符串或 unicode 的数组。

## 返回值
`ndarray` : 布尔的输出数组。

## 代码示例 #1
```py
# Python program explaining
# numpy.char.isnumeric() method

import numpy as geek

# input array contains only numeric character
in_arr = geek.array([ '1000', '2000'] )
print ("Input array : ", in_arr)

out_arr = geek.char.isnumeric(in_arr)
print ("Output array: ", out_arr)
```

**输出:**
```py
Input array :  ['1000' '2000']
Output array:  [ True  True]
```

## 代码示例 #2
```py
# Python program explaining
# numpy.char.isnumeric() method

import numpy as geek

# input array
in_arr = geek.array([ 'python3.5', 'a1000', '1234 ab'] )
print ("Input array : ", in_arr)

out_arr = geek.char.isnumeric(in_arr)
print ("Output array: ", out_arr)
```

**输出:**
```py
Input array :  ['python3.5' 'a1000' '1234 ab']
Output array:  [False False False]
```