# numpy.defchararray.add() 用法详解

> 参考链接：https://www.geeksforgeeks.org/numpy-defchararray-python/

`numpy.core.defchararray.add(arr1, arr2)`：对两个字符串数组进行元素级串联。

## 参数
- `arr1`：数组状或字符串。
- `arr2`：数组状或字符串。

## 返回值
返回连接后的字符串数组。

## 代码示例

### 代码#1

```py
# Python Program illustrating 
# numpy.char.add() method 
import numpy as np

arr1 = ['vdteteAAAa', 'AAAttttds', 'AAaxtt']
arr2 = ['1111sfdsf', '1111111sdsf2', '1111111sfsf2']

print ("\narr1 : ", arr1)
print ("\narr2 : ", arr2)

print ("\narr1 + arr2\n", np.char.add(arr1, arr2))
print ("\narr2 + arr1\n", np.char.add(arr2, arr1))
```

**输出:**

```py
arr1 :  ['vdteteAAAa', 'AAAttttds', 'AAaxtt']

arr2 :  ['1111sfdsf', '1111111sdsf2', '1111111sfsf2']

arr1 + arr2
 ['vdteteAAAa1111sfdsf' 'AAAttttds1111111sdsf2' 'AAaxtt1111111sfsf2']

arr2 + arr1
 ['1111sfdsfvdteteAAAa' '1111111sdsf2AAAttttds' '1111111sfsf2AAaxtt']
```

### 代码#2

```py
# Python Program illustrating 
# numpy.char.add() method 
import numpy as np

arr1 = 'This is geeks '
arr2 = 'for geeks '

print ("\narr1 + arr2\n", np.char.add(arr1, arr2))
print ("\narr2 + arr1\n", np.char.add(arr2, arr1))
```

**输出:**

```py
arr1 + arr2
 This is geeks for geeks

arr2 + arr1
 for geeks This is geeks
```