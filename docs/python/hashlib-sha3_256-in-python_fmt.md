# Python 中的 `hashlib.sha3_256()`

> 原文:[https://www.geeksforgeeks.org/hashlib-sha3_256-in-python/](https://www.geeksforgeeks.org/hashlib-sha3_256-in-python/)

借助`hashlib.sha3_256()`方法，我们可以将字节格式的正常字符串转换为加密形式。借助`hashlib.sha3_256()`方法，可以将密码和重要文件转换成哈希来保护它们。

## 语法与返回

> **语法:** `hashlib.sha3_256()`
> **返回:**返回字符串的哈希代码。

## 示例 1

在这个示例中，我们可以看到，通过使用`hashlib.sha3_256()`方法，我们能够对字节字符串或密码进行加密，以使用该方法来保护它们。

```py
# import hashlib
import hashlib

# Using hashlib.sha3_256() method
gfg = hashlib.sha3_256()
gfg.update(b'GeeksForGeeks')

print(gfg.digest())
```

**输出:**

> b' \x14\xf7h\xf7\xb2w<\xe5\x8FQ\xe9sI\xd0\x89\x1c$\xfe\xac\xdfv\xe8c|\xb9\xdf\x96\xe3\x93z '

## 示例 2

```py
# import hashlib
import hashlib

# Using hashlib.sha3_256() method
gfg = hashlib.sha3_256()
gfg.update(b'xyz@1234_GFG')

print(gfg.digest())
```

**输出:**

> b"b\xea\x7f\x8a\xd3\x93\xb1k\x5t5\xa5j|\xea\xad\x03\xc8\x9egw\xdew\x03\xa6\xb8\x85}\xd5~\xb6"