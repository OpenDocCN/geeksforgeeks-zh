# numpy 字符串操作

## isspace() 函数

> 原文: [https://www.geeksforgeeks.org/numpy-string-operations-isspace-function/](https://www.geeksforgeeks.org/numpy-string-operations-isspace-function/)

`numpy.core.defchararray.isspace(arr)` 函数用于检查字符串中的每个元素。如果字符串中只包含空白字符且至少有一个字符，则为该元素返回 `True`；否则返回 `False`。

### 语法
```python
numpy.core.defchararray.isspace(arr)
```

### 参数
- **arr** : 类似字符串或 unicode 的数组。

### 返回值
- **ndarray** : 布尔值的输出数组。

### 代码示例

**代码#1：**
```py
# Python program explaining
# numpy.char.isspace() method

import numpy as geek

# input arrays  not containing any space
in_arr = geek.array([ 'Geeksforgeeks', 'Codechef'] )
print ("Input array : ", in_arr)

out_arr = geek.char.isspace(in_arr)
print ("Output array: ", out_arr)
```

**输出：**
```py
Input array :  ['Geeksforgeeks' 'Codechef']
Output array:  [False False]
```

**代码#2：**
```py
# Python program explaining
# numpy.char.isspace() method

import numpy as geek

# input arrays containing string along with space
in_arr = geek.array([ 'Geeks\nfor\ngeeks', 'Code\tchef'] )
print ("Input array : ", in_arr)

out_arr = geek.char.isspace(in_arr)
print ("Output array: ", out_arr)
```

**输出：**
```py
Input array :  ['Geeks\nfor\ngeeks' 'Code\tchef']
Output array:  [False False]
```

**代码#3：**
```py
# Python program explaining
# numpy.char.isspace() method

import numpy as geek

# input arrays containing only white space
in_arr = geek.array([ '\n', '\t', ' ', '\n\t '] )
print ("Input array : ", in_arr)

out_arr = geek.char.isspace(in_arr)
print ("Output array: ", out_arr)
```

**输出：**
```py
Input array :  ['\n' '\t' ' ' '\n\t ']
Output array:  [ True  True  True  True]
```