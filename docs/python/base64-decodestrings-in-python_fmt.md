# Python中的base64解码

> 原文：[https://www.geeksforgeeks.org/base64-decodestrings-in-python/](https://www.geeksforgeeks.org/base64-decodestrings-in-python/)

借助`base64.decodestring(s)`方法，我们可以借助base64数据将二进制字符串解码成范式。

## 语法
> `base64.decodestring(b_string)`

**返回:** 返回解码后的字符串。

## 示例#1
在这个示例中，我们可以看到，通过使用`base64.decodestring(s)`方法，我们能够通过使用该方法获得可以是二进制形式的解码字符串。

```python
# import base64
from base64 import encodestring
from base64 import decodestring

s = b'GeeksForGeeks'
s = encodestring(s)
# Using base64.decodestring(s) method
gfg = decodestring(s)

print(gfg)
```

**输出:**
> b'GeeksForGeeks

## 示例#2

```python
# import base64
from base64 import encodestring
from base64 import decodestring

s = b'Hello World'
s = encodestring(s)
# Using base64.decodestring(s) method
gfg = decodestring(s)

print(gfg)
```

**输出:**
> b'Hello World'