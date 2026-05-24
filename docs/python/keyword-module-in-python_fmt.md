# Python 中的关键字模块

> 原文: [https://www.geeksforgeeks.org/keyword-module-in-python/](https://www.geeksforgeeks.org/keyword-module-in-python/)

[Python](https://www.geeksforgeeks.org/python-programming-language/) 提供内置模块 `keyword`，可以了解 Python 的保留关键字。

`keyword` 模块允许您了解 Python 的保留字或关键字，并检查变量值是否是保留字。如果您不知道 Python 的所有关键字，您可以使用这个模块来检索这些信息。此外，它还可以帮助您通过在 Python shell 模式下使用其功能来检查一个单词是否是关键字。

## 该模块的功能有:

### `keyword.iskeyword(parameter)`

此函数如果传入的参数是 Python 关键字则返回 `True`，否则返回 `False`。参数可以是一个字符串或存储字符串的变量。它会相应地将参数与语言中定义的 Python 关键字进行比较并返回输出。

**示例:**

```py
# Program to check whether a given
# word is a Python keyword or not

import keyword

s = "if"
t = "in"
u = "GeeksforGeeks"

# using iskeyword() function to check
print(s, "is a keyword in Python:",
      keyword.iskeyword(s))

print("lambda is a keyword in Python:",
      keyword.iskeyword("lambda"))

print("print is a keyword in Python:",
      keyword.iskeyword("print"))

print(t, "is a keyword in Python:",
      keyword.iskeyword(t))

print(u, "is a keyword in Python:",
      keyword.iskeyword(u))
```

**输出:**

```py
if is a keyword in Python: True
lambda is a keyword in Python: True
print is a keyword in Python: False
in is a keyword in Python: True
GeeksforGeeks is a keyword in Python: False
```

从上面的例子可以看出，变量 `s` 和 `t` 的值是 Python 中的一个关键字，因此函数返回 `True`。同样，字符串 `GeeksforGeeks` 不是关键字，因此函数返回 `False`。

### `keyword.kwlist`

这是 `keyword` 模块的一个预定义变量，存储了 Python 的所有关键字。因此，只需调用它就可以显示 Python 的所有关键字。

**示例:**

```py
# Program to display the list of Python keywords

# importing keyword module
import keyword

# using keyword.kwlist to display the list of keywords
print(keyword.kwlist)
```

**输出:**

> ['and', 'as', 'assert', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'exec', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'not', 'or', 'pass', ...

**注意:** `keyword.kwlist` 不是函数，因此不使用括号。`kwlist` 是之前在 `keyword` 模块中定义的变量。