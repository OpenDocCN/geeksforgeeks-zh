# 如何在 Python 中找到对象的大小？

> 原文：`https://www.geeksforgeeks.org/how-to-find-size-of-an-object-in-python/`

## 介绍

使用 `sys.getsizeof()` 可以找到在内存中占据一定空间的特定对象的存储大小。该函数返回对象的大小，单位为*字节*。它最多需要两个参数，即对象本身。

**注：** 只核算直接归属于对象的内存消耗，不核算其所指对象的内存消耗。

## 示例

```py
Input: 
# Any Integer Value
sys.getsizeof(4)

Expected Output: 4 bytes (Size of integer is 4bytes)

Actual Output: 28 bytes
```

下面是我们如何解释实际输出。请看下表：

| object type | actual size | annotate |
| --- | --- | --- |
| int | 28 | - |
| str | 49 | +1 Each additional character (total length of 49+ characters) |
| tuple | 216 | 0-4 take the size of 216. 5-19 will take 728. 20th will take 2264 and so on ... |
| list | 56 (empty list) | +8 for each additional item in the list (total length of 56+8 * characters) |
| set | 216 | - |
| dict | 232 | 0-5 take the size of 232. 6-10 will be 360. 11th will take 640 and so on ... |
| function definition | 136 | No attributes and default parameters |

## 更多示例

```py
import sys

a=sys.getsizeof(12) 
print(a)

b=sys.getsizeof('geeks')
print(b)

c=sys.getsizeof(('g','e','e','k','s'))
print(c)

d=sys.getsizeof(['g','e','e','k','s'])
print(d)

e=sys.getsizeof({1,2,3,4})
print(e)

f=sys.getsizeof({1:'a',2:'b',3:'c',4:'d'})
print(f)
```

## 输出

```py

```