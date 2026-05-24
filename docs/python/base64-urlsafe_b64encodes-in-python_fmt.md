# Python 中的 `base64.urlsafe_b64encode`

> 原文: [https://www.geeksforgeeks.org/base64-urlsafe_b64encodes-in-python/](https://www.geeksforgeeks.org/base64-urlsafe_b64encodes-in-python/)

借助 `base64.urlsafe_b64encode(s)` 方法，我们可以使用 URL 和文件系统安全字母将字符串编码成二进制形式。

> **语法:** `base64.urlsafe_b64encode(s)`
>
> **返回:** 返回编码后的字符串。

## 示例 #1

在这个示例中，我们可以看到，通过使用 `base64.urlsafe_b64encode(s)` 方法，我们能够获得可以是二进制形式的编码字符串。

```py
# import base64
from base64 import urlsafe_b64encode

s = b'GeeksForGeeks'
# Using base64.urlsafe_b64encode(s) method
gfg = urlsafe_b64encode(s)

print(gfg)
```

**输出:**

> b'R2Vla3NGb3JHZWVrcw=='

## 示例 2

```py
# import base64
from base64 import urlsafe_b64encode

s = b'www.python.org/documentation'
# Using base64.urlsafe_b64encode(s) method
gfg = urlsafe_b64encode(s)

print(gfg)
```

**输出:**

> b'd3d3LnB5dGhvbi5vcmcvZG9jdW1lbnRhdGlvbg=='