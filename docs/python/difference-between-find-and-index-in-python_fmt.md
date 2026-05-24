# Python 中 `find()` 和 `index()` 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-find-and-index-in-python/](https://www.geeksforgeeks.org/difference-between-find-and-index-in-python/)

在 Python 中，要查找字符串中子字符串的索引，可以通过 Python 的内置函数使用 `find()` 或 `index()` 来定位。两者都返回字符串中子字符串的起始索引（如果存在的话）。这篇文章讨论了什么时候用哪个，为什么用。

## `index()` 函数

`index()` 方法返回字符串中的子字符串或字符的索引（如果找到的话）。如果未找到子字符串或字符，将引发异常。

**语法：**

```py
string.index(<substring>)
```

**示例：**

```py
string = 'geeks for geeks'

# returns index value
result = string.index('for')
print("Substring for:", result)

result3 = string.index("best")
print("substring best:", result3)
```

**输出：**

```
Substring for: 6
Traceback (most recent call last):
  File "<string>", line 8, in <module>
ValueError: substring not found
```

## `find()` 方法

`find()` 方法返回子字符串或字符（如果找到）的第一个匹配项的索引。如果没有找到，它返回 `-1`。

**语法：**

```py
string.find(<substring>)
```

**示例：**

```py
string = 'geeks for geeks'

# returns index value
result = string.find('for')
print("Substring for:", result)

result = string.find('best')
print("Substring best:", result)
```

**输出：**

```
Substring for: 6
Substring best: -1
```

## `index()` 和 `find()` 之间的差异表

| **`index()`** | **`find()`** |
| --- | --- |
| 如果未找到子字符串，则返回异常 | 如果未找到子字符串，则返回 `-1` |
| 如果您不确定子字符串的存在，就不应该使用它 | 当您不确定子串是否存在时，这是正确的函数 |
| 这可以应用于字符串、列表和元组 | 这只能应用于字符串 |
| 它不能与条件语句一起使用 | 如果找到了子字符串，它可以与条件语句一起执行语句，如果没有找到子字符串，它也可以执行语句 |