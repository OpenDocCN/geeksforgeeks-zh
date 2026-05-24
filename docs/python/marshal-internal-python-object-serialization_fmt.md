# 封送—内部 Python 对象序列化

> 原文：[https://www.geeksforgeeks.org/marshal-internal-python-object-serialization/](https://www.geeksforgeeks.org/marshal-internal-python-object-serialization/)

序列化数据意味着将其转换为一个字节字符串，然后再从这个字符串中重建它。如果数据完全由基本的 Python 对象组成，序列化数据的最快方法是使用封送模块（对于用户定义的类，[Pickle](https://www.geeksforgeeks.org/pickle-python-object-serialization/) 应该是首选）。封送模块包含能够以二进制格式读写 Python 值的函数。

`marshal` 模块的存在主要是为了支持对 Python 模块进行“伪编译”代码的读写（`.pyc` 文件）。该模块不支持所有 Python 对象类型。

支持以下类型：布尔值、整数、浮点数、复数、字符串、字节、字节数组、元组、列表、集合、frozen set、字典和代码对象，其中应该理解，元组、列表、集合、frozen set 和字典仅在其中包含的值本身被支持的情况下才被支持。单例 `None`、省略号和停止迭代也可以被封送和解封。

## 功能

### `marshal.version`
表示模块使用的格式。
*   版本 0 – 历史格式
*   版本 1 – 共享内部字符串
*   版本 2 – 对浮点数使用二进制格式
*   版本 3 – 支持对象实例化和递归
*   版本 4 – 当前版本

### `marshal.dumps(value[, version])`
该函数返回一个字节对象，该对象与 `dump(value, file)` 写入文件的内容相同。`version` 参数指示 `dumps` 应使用的数据格式。如果 `value` 具有（或包含一个具有）不支持的类型，则会引发 `ValueError` 异常。

**示例**

```python
# Python code to demonstrate serialization
import marshal

data = {12:'twelve', 'feep':list('ciao'), 1.23:4+5j,
        (1,2,3):u'wer'}
bytes = marshal.dumps(data)

print (bytes)
```

**输出**

```python
b'\xd3\xf5\x12\x00\x00\x00\x12\x00\x00\x00\x0c\x00\x00\x00\x04\x00\x00\x00\x01\x00\x00\x00\x02\x00\x00\x00\x03\x00\x00\x00\x03\x00\x00\x00wer\x04\x00\x00\x00feep\x04\x00\x00\x00ciao\x01\x00\x00\x00\x04\x00\x00\x00twelve\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\xf0?\x00\x00\x00\x00\x00\x00\x10@\x00\x00\x00\x00\x00\x00\x14@'
```

### `marshal.loads(bytes)`
此函数可以通过将类字节对象转换回一个值来重建数据。如果未找到值，则引发 `EOFError`、`ValueError` 或 `TypeError`。

**示例**

```python
# Python code to demonstrate de-serialization
import marshal

data = {12:'twelve', 'feep':list('ciao'), 1.23:4+5j,
        (1,2,3):u'wer'}
bytes = marshal.dumps(data)
redata = marshal.loads(bytes)

print (redata)
```

**输出**

```python
{12: 'twelve', 1.23: (4+5j), 'feep': ['c', 'i', 'a', 'o'], (1, 2, 3): 'wer'}
```

### `marshal.dump(value, file[, version])`
此函数用于在打开的可写二进制文件上写入支持的类型值。如果值的类型不受支持，则会引发 `ValueError` 异常。

### `marshal.load(file)`
这个函数从打开的可读二进制文件中读取一个值并返回。如果未读取任何值，将引发 `EOFError`、`ValueError` 或 `TypeError`。

本文由**阿迪提·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。