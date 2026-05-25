## Python 中的 numpy.ndarray.byteswap()

> 原文链接: https://www.geeksforgeeks.org/ndarray-byteswap-in-python/

`numpy.ndarray.byteswap()` 函数通过返回一个 byteswapped 数组，在低端和大端数据表示之间切换，可选地就地交换。

**语法:**
`ndarray.byteswap(inplace=False)`

**参数:**
**inplace**: 【bool，可选】如果为真，就地交换字节，默认为假。

**返回:**
**out**: 【ndarray】字节数组。如果 `inplace` 为真，这就是对自己的看法。

**代码#1:**

```py
# Python program explaining 
# byteswap() function
import numpy as geek

# a is an array of integers.
a = geek.array([1, 256, 100], dtype = np.int16)

print(a.byteswap(True))
```

**输出:**

```py
[256  1  25600]
```

**代码#2:** `byteswap()`函数不适用于字符串数组。

```py
# Python program explaining 
# byteswap() function
import numpy as geek

# a is an array of strings
a = geek.array(["arka","soumen","simran"],dtype = np.int16)

print(a.byteswap(True))
```

**输出:**

```py
ValueError                                Traceback (most recent call last)
 in <module>()
      1 import numpy as geek
----> 2 a = geek.array(["arka","soumen","simran"],dtype = np.int16)

4 #a is an array of strings

ValueError: invalid literal for int() with base 10: 'arka'
```