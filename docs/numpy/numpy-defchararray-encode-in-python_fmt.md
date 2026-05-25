# numpy.defchararray.encode() 用法详解

## 函数描述

`numpy.core.defchararray.encode(arr, encoding)`：这个 numpy 函数根据指定的编解码器对字符串（对象）进行编码。

## 参数

- `arr`：阵列或字符串。
- `encoding`：【str】跟随的编码名称。
- `errors`：指定如何处理错误。

## 返回值

编码字符串。

## 代码示例

```py
# Python Program illustrating 
# numpy.char.encode() method 
import numpy as np

arr1 = ['eAAAa', 'ttttds', 'AAtAAt']
arr2 = ['11sf', 'sdsf2', '1111f2']

# Printing the array
print ("\narr1 : ", arr1)
print ("\narr2 : ", arr2)

print ("\nEncoded arr1 : \n", np.char.encode(arr1, encoding ='cp037'))
print ("\nEncoded arr2 : \n", np.char.encode(arr2, encoding ='utf8'))
print ("\nEncoded arr2 : \n", np.char.encode(arr2, encoding ='utf8', 
                                            errors = 'strict'))
```

## 输出结果

```py
arr1 :  ['eAAAa', 'ttttds', 'AAtAAt']
arr2 :  ['11sf', 'sdsf2', '1111f2']

Encoded arr1 : 
 [b'\x85\xc1\xc1\xc1\x81' b'\xa3\xa3\xa3\xa3\x84\xa2'
 b'\xc1\xc1\xa3\xc1\xc1\xa3']

Encoded arr2 : 
 [b'11sf' b'sdsf2' b'1111f2']

Encoded arr2 : 
 [b'11sf' b'sdsf2' b'1111f2']
```