# Python 位函数对 int（位长、to 字节和 from 字节）

> 原文：[https://www.geeksforgeeks.org/python-bit-functions-on-int-bit_length-to_bytes-and-from_bytes/](https://www.geeksforgeeks.org/python-bit-functions-on-int-bit_length-to_bytes-and-from_bytes/)

`int` 类型实现了 `numbers.Integral` 抽象基类。

## 1. `int.bit_length()`
返回用二进制表示整数所需的位数，不包括符号和前导零。

要演示的代码：
```py
num = 7
print(num.bit_length())

num = -7
print(num.bit_length())
```

**Output:**
```py
3
3
```

## 2. `int.to_bytes(length, byteorder, *, signed=False)`
返回一个表示整数的字节数组。如果 `byteorder` 为 `"big"`，则最高有效字节位于字节数组的开头。如果 `byteorder` 为 `"little"`，则最高有效字节位于字节数组的末尾。`signed` 参数确定是否使用二进制补码来表示整数。

```py
# Returns byte representation of 1024 in a
# big endian machine.
print((1024).to_bytes(2, byteorder='big'))
```

**Output:**
```py
b'\x04\x00'
```

## 3. `int.from_bytes(bytes, byteorder, *, signed=False)`
返回给定字节数组表示的整数。

```py
# Returns integer value of '\x00\x10' in big endian machine.
print(int.from_bytes(b'\x00\x10', byteorder='big'))
```

**Output:**
```py
16
```